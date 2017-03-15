---
title: "Практическое руководство. Определение и установка глобального обработчика исключений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработчики, общие"
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Практическое руководство. Определение и установка глобального обработчика исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода показано, как необработанные исключения можно заключить.  Пример формы, которая содержит кнопку, отжиманный выполняет пустую ссылку, вызывает исключение делегатом.  Эта функция представляет ultimate сбой кода.  Результирующее исключение обработано на уровне приложения обработчиком исключений задать основной функцией.  
  
 Это достигается путем связывания делегата для события <xref:System.Windows.Forms.Application.ThreadException>.  В этом случае следующие исключения затем передаются методу `App::OnUnhandled`.  
  
## Пример  
  
```  
// global_exception_handler.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Drawing;  
using namespace System::Windows::Forms;  
  
ref class MyForm : public Form  
{  
   Button^ b;  
public:  
   MyForm( )  
   {  
      b = gcnew Button( );  
      b->Text = "Do Null Access";  
      b->Size = Drawing::Size(150, 30);  
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);  
      Controls->Add(b);  
   }  
   void OnClick(Object^ sender, EventArgs^ args)   
   {  
      // do something illegal, like call through a null pointer...  
      Object^ o = nullptr;  
      o->ToString( );        
   }  
};  
  
ref class App  
{  
public:  
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)  
   {  
      MessageBox::Show(e->Exception->Message, "Global Exeception");  
      Application::ExitThread( );  
   }  
};  
  
int main()  
{  
   Application::ThreadException += gcnew   
      ThreadExceptionEventHandler(App::OnUnhandled);  
  
   MyForm^ form = gcnew MyForm( );  
   Application::Run(form);  
}  
```  
  
## См. также  
 [Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)