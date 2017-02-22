---
title: "Помеченные операторы | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "goto"
  - "case"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "labeled - оператор"
  - "операторы, с меткой"
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Помеченные операторы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Метки используются для передачи управления программой непосредственно указанному оператору.  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 Областью метки является вся функция, в которой она объявлена.  
  
## Заметки  
 Существует три типа операторов с метками.  Во всех для отделения метки от оператора используется двоеточие.  Метки case и default предназначены для операторов case.  
  
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
  
 **Оператор goto**  
  
 Появление метки *идентификатора* в программе исходного кода объявляет метку.  Только оператор [goto](../cpp/goto-statement-cpp.md) может передать контроль метке *идентификатора*.  Следующий фрагмент кода иллюстрирует использование оператора `goto` и метки *идентификатора*:  
  
 Метка не может отображаться самостоятельно, она всегда прикреплена к оператору.  Если необходимо использовать метку самостоятельно, поместите оператор null после метки.  
  
 Метка имеет область функции и не может быть повторно объявлена в пределах функции.  Однако одно и то же имя может использоваться как метка в разных функциях.  
  
```  
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
  
 **Оператор case**  
  
 Метки, которые отображаются после ключевого слова **case**, не могут также отображаться за пределами оператора `switch`.  \(Это ограничение также применяется к ключевому слову **default**.\) В следующем фрагменте кода показано правильное использование меток **case**.  
  
```  
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
  
## Метки в операторе case  
 Метки, которые отображаются после ключевого слова **case**, не могут также отображаться за пределами оператора `switch`.  \(Это ограничение также применяется к ключевому слову **default**.\) В следующем фрагменте кода показано правильное использование меток **case**.  
  
```  
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
  
## Метки в операторе goto  
 Появление метки *идентификатора* в программе исходного кода объявляет метку.  Только оператор [goto](../cpp/goto-statement-cpp.md) может передать контроль метке *идентификатора*.  Следующий фрагмент кода иллюстрирует использование оператора `goto` и метки *идентификатора*:  
  
 Метка не может отображаться самостоятельно, она всегда прикреплена к оператору.  Если необходимо использовать метку самостоятельно, поместите оператор null после метки.  
  
 Метка имеет область функции и не может быть повторно объявлена в пределах функции.  Однако одно и то же имя может использоваться как метка в разных функциях.  
  
```  
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
  
## См. также  
 [Общие сведения об операторах в C\+\+](../cpp/overview-of-cpp-statements.md)   
 [Оператор switch \(C\+\+\)](../cpp/switch-statement-cpp.md)