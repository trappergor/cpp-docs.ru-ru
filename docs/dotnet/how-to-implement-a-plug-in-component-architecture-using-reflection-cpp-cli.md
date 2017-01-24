---
title: "Практическое руководство. Реализация архитектуры с подключаемыми компонентами с помощью отражения (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "подключаемые модули [C++]"
  - "отражение [C++], подключаемые модули"
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Реализация архитектуры с подключаемыми компонентами с помощью отражения (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующих примерах кода показаны способы использования отражения для реализации простой "подключаемой" архитектуры.  Первый перечень содержит список приложений, а второй — подключаемый модуль.  Приложение является формой нескольких документов, которые заполняются с помощью классов на основе форм, предоставляемых подключаемой библиотекой DLL в качестве аргументов командной строки.  
  
 Предложение пытается загрузить предоставляемую сборку с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.  В случае успешной загрузки типы в сборке перечисляются с помощью метода <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>.  Затем каждый тип проверяется на предмет совместимости с помощью метода <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName>.  В приведенном примере классы в предоставленной сборке, чтобы считаться подключаемыми модулями, должны являться производными от класса <xref:System.Windows.Forms.Form>.  
  
 Затем создаются экземпляры совместимых классов с помощью метода <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>, который принимает <xref:System.Type> в качестве аргумента и возвращает указатель новому экземпляру.  Каждый новый экземпляр затем прикрепляется к форме и отображается.  
  
 Обратите внимание, что метод <xref:System.Reflection.Assembly.Load%2A> не принимает имена сборок, которые содержат расширение файла.  Основная функция приложения обрезает любые предоставленные расширения, поэтому в любом случае будет выполняться следующий код.  
  
## Пример  
 Следующий код определяет приложение, которое принимает подключаемые модули.  В качестве первого аргумента необходимо предоставить имя сборки.  Эта сборка должна содержать как минимум один открытый тип, производный от типа <xref:System.Windows.Forms.Form>.  
  
```  
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
## Пример  
 Следующий код определяет три класса, производные от <xref:System.Windows.Forms.Form>.  Если имя результирующей сборки будет передано исполняемому файлу из предыдущего перечня, все три класса будут обнаружены и для каждого из них будет создан экземпляр, несмотря на то что все они неизвестны ведущему приложению во время компиляции.  
  
```  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  
  
## См. также  
 [Отражение](../dotnet/reflection-cpp-cli.md)