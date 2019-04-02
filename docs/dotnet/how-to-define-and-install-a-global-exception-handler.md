---
title: Практическое руководство. Определение и Установка глобального обработчика исключений
ms.date: 11/04/2016
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
ms.openlocfilehash: d1b8452d19172bf16817c36032189accfd855539
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777212"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>Практическое руководство. Определение и Установка глобального обработчика исключений

В следующем примере кода показано, как необработанные исключения могут быть захвачены. Пример формы содержит кнопку, при нажатии выполняет ссылкой на null, вызывая исключение, исключение. Эта функция представляет типичный код сбоя. Результирующее исключение перехватывается обработчиком исключений для всего приложения, установленные в основной функции.

Это достигается путем привязки делегата к <xref:System.Windows.Forms.Application.ThreadException> событий. В этом случае исключений, затем отправляются `App::OnUnhandled` метод.

## <a name="example"></a>Пример

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

## <a name="see-also"></a>См. также

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)
