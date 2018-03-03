---
title: "Помеченные операторы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 139b94ab0287de5449e0b03ca96f5443049cfb5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="labeled-statements"></a>Операторы с метками
Метки используются для передачи управления программой непосредственно указанному оператору.  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 Областью метки является вся функция, в которой она объявлена.  
  
## <a name="remarks"></a>Примечания  
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
  
 **Оператор goto**  
  
 Внешний вид *идентификатор* метки в исходном коде программы объявляет метку. Только [goto](../cpp/goto-statement-cpp.md) инструкция может передать контроль *идентификатор* метки. В следующем фрагменте кода показано использование `goto` инструкции и *идентификатор* метку:  
  
 Метка не может отображаться самостоятельно, она всегда прикреплена к оператору. Если необходимо использовать метку самостоятельно, поместите оператор null после метки.  
  
 Метка имеет область функции и не может быть повторно объявлена в пределах функции. Однако одно и то же имя может использоваться как метка в разных функциях.  
  
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
  
 **Инструкция case**  
  
 Метки, которые появляются после **случай** ключевое слово не может также отображаться за пределами `switch` инструкции. (Это ограничение также применяется к **по умолчанию** ключевое слово.) В следующем фрагменте кода показано правильное использование **случай** метки:  
  
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
  
## <a name="labels-in-the-case-statement"></a>Метки в операторе case  
 Метки, которые появляются после **случай** ключевое слово не может также отображаться за пределами `switch` инструкции. (Это ограничение также применяется к **по умолчанию** ключевое слово.) В следующем фрагменте кода показано правильное использование **случай** метки:  
  
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
  
## <a name="labels-in-the-goto-statement"></a>Метки в операторе goto  
 Внешний вид *идентификатор* метки в исходном коде программы объявляет метку. Только [goto](../cpp/goto-statement-cpp.md) инструкция может передать контроль *идентификатор* метки. В следующем фрагменте кода показано использование `goto` инструкции и *идентификатор* метку:  
  
 Метка не может отображаться самостоятельно, она всегда прикреплена к оператору. Если необходимо использовать метку самостоятельно, поместите оператор null после метки.  
  
 Метка имеет область функции и не может быть повторно объявлена в пределах функции. Однако одно и то же имя может использоваться как метка в разных функциях.  
  
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
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)   
 [Оператор switch (C++)](../cpp/switch-statement-cpp.md)