---
title: Операторы с метками
ms.date: 11/04/2016
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
ms.openlocfilehash: d971a0e9864aeada1db5f004ef70577512e78c76
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179696"
---
# <a name="labeled-statements"></a>Операторы с метками

Метки используются для передачи управления программой непосредственно указанному оператору.

```
identifier :  statement
case constant-expression :  statement
default :  statement
```

Областью метки является вся функция, в которой она объявлена.

## <a name="remarks"></a>Remarks

Существует три типа операторов с метками. Во всех для отделения метки от оператора используется двоеточие. Метки case и default предназначены для операторов case.

```cpp
#include <iostream>
using namespace std;

void test_label(int x) {

    if (x == 1){
        goto label1;
    }
    goto label2;

label1:
    cout << "in label1" << endl;
    return;

label2:
    cout << "in label2" << endl;
    return;
}

int main() {
    test_label(1);  // in label1
    test_label(2);  // in label2
}
```

**Оператор GoTo**

Внешний вид метки *идентификатора* в исходной программе объявляет метку. Только оператор [goto](../cpp/goto-statement-cpp.md) может передавать управление метке *идентификатора* . В следующем фрагменте кода показано использование оператора **goto** и метки *идентификатора* .

Метка не может отображаться самостоятельно, она всегда прикреплена к оператору. Если необходимо использовать метку самостоятельно, поместите оператор null после метки.

Метка имеет область функции и не может быть повторно объявлена в пределах функции. Однако одно и то же имя может использоваться как метка в разных функциях.

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
}

//Output: At Test2 label.
```

**Оператор Case**

Метки, которые появляются после ключевого слова **case** , также не могут использоваться за пределами оператора **switch** . (Это ограничение также применяется к ключевому слову **по умолчанию** .) В следующем фрагменте кода показано правильное использование меток **вариантов** .

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );
      EndPaint( hWnd, &ps );
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-case-statement"></a>Метки в операторе case

Метки, которые появляются после ключевого слова **case** , также не могут использоваться за пределами оператора **switch** . (Это ограничение также применяется к ключевому слову **по умолчанию** .) В следующем фрагменте кода показано правильное использование меток **вариантов** .

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      // Obtain a handle to the device context.
      // BeginPaint will send WM_ERASEBKGND if appropriate.

      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );

      // Inform Windows that painting is complete.

      EndPaint( hWnd, &ps );
      break;

   case WM_CLOSE:
      // Close this window and all child windows.

      KillTimer( hWnd, TIMER1 );
      DestroyWindow( hWnd );
      if ( hWnd == hWndMain )
         PostQuitMessage( 0 );  // Quit the application.
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-goto-statement"></a>Метки в операторе goto

Внешний вид метки *идентификатора* в исходной программе объявляет метку. Только оператор [goto](../cpp/goto-statement-cpp.md) может передавать управление метке *идентификатора* . В следующем фрагменте кода показано использование оператора **goto** и метки *идентификатора* .

Метка не может отображаться самостоятельно, она всегда прикреплена к оператору. Если необходимо использовать метку самостоятельно, поместите оператор null после метки.

Метка имеет область функции и не может быть повторно объявлена в пределах функции. Однако одно и то же имя может использоваться как метка в разных функциях.

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
// At Test2 label.
}
```

## <a name="see-also"></a>См. также раздел

[Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)<br/>
[Оператор switch (C++)](../cpp/switch-statement-cpp.md)
