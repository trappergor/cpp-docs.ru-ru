---
title: "Реализации архитектуры подключаемых модулей (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- plug-ins [C++]
- reflection [C++}, plug-ins
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 05c6c2584e39ed145a30c919ed850aac45905a85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-implement-a-plug-in-component-architecture-using-reflection-ccli"></a>Практическое руководство. Реализация архитектуры с подключаемыми компонентами с помощью отражения (C++/CLI)
В следующем примере кода показано использование отражения для реализации простой «подключаемой» архитектуры. Первый листинг — это приложение, а второй — подключаемый модуль. Приложение является формой нескольких документов, которые заполняются с помощью любого форм классы, находящиеся в библиотеке DLL подключаемого модуля, предоставленный аргумент командной строки.  
  
 Приложение пытается загрузить предоставляемую сборку с помощью <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> метод. При успешном выполнении типы в сборке перечисляются с помощью <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> метод. Каждый тип затем проверяется на совместимость с помощью <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> метод. В этом примере классы в предоставленной сборке должен быть производным от <xref:System.Windows.Forms.Form> класса, чтобы считаться подключаемыми модулями.  
  
 Совместимые классы затем инициализируются с <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> метод, который принимает <xref:System.Type> в качестве аргумента и возвращает указатель на новый экземпляр. Каждый новый экземпляр затем прикрепляется к форме и отображается.  
  
 Обратите внимание, что <xref:System.Reflection.Assembly.Load%2A> метод не принимает имена сборок, которые включают расширение файла. Функция main в приложении Обрезка любые предоставленные расширения, поэтому в следующем примере код работает в любом случае.  
  
## <a name="example"></a>Пример  
 Следующий код определяет приложение, которое принимает подключаемые модули. Имя сборки необходимо указать в качестве первого аргумента. Эта сборка должна содержать по крайней мере один открытый <xref:System.Windows.Forms.Form> производный тип.  
  
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
  
## <a name="example"></a>Пример  
 Следующий код определяет три класса, производного от <xref:System.Windows.Forms.Form>. Если результирующее имя сборки передается к исполняемому файлу в предыдущем примере, каждая из этих трех классов будут обнаружены и экземпляр, несмотря на то, что все они неизвестны ведущему приложению во время компиляции.  
  
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
  
## <a name="see-also"></a>См. также  
 [Отражение (C++/CLI)](../dotnet/reflection-cpp-cli.md)