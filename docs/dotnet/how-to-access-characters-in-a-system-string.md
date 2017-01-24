---
title: "Практическое руководство. Доступ к символам объекта System::String | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "знаки [C++], доступ в System::String"
  - "примеры [C++], строки"
  - "строки [C++], доступ к знакам"
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Доступ к символам объекта System::String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Существует возможность доступа к символам объекта <xref:System.String> для выполнения высокопроизводительных запросов к неуправляемым функциям, принимающим в качестве параметров строки `wchar_t*`.  Метод возвращает внутренний указатель на первый символ объекта <xref:System.String>.  С этим указателем можно работать напрямую, либо же его можно закрепить и передать функции, принимающей в качестве параметра обычную строку `wchar_t`.  
  
## Пример  
 Функция `PtrToStringChars` возвращает <xref:System.Char>, который является внутренним указателем \(также известным как `byref`\).  В этом качестве к нему применима процедура сборки мусора.  Этот указатель следует закреплять, только если необходимо передать его собственной функции.  
  
 Рассмотрим следующий код.  Закрепление не требуется, поскольку `ppchar` является внутренним указателем, и если сборщик мусора переместит строку, на которую он указывает, будет также выполнено обновление `ppchar`.  Код будет работать без использования [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md), причем отсутствует риск снижения производительности, связанный с закреплением.  
  
 При передаче `ppchar`  собственной функции указатель должен быть закрепленным, поскольку сборщик мусора неспособен обновлять указатели в неуправляемом кадре стека.  
  
```  
// PtrToStringChars.cpp  
// compile with: /clr  
#include<vcclr.h>  
using namespace System;  
  
int main() {  
   String ^ mystring = "abcdefg";  
  
   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );  
  
   for ( ; *ppchar != L'\0'; ++ppchar )  
      Console::Write(*ppchar);  
}  
```  
  
  **abcdefg**   
## Пример  
 В данном примере демонстрируются случаи, когда использование закрепления является необходимым.  
  
```  
// PtrToStringChars_2.cpp  
// compile with: /clr  
#include <string.h>  
#include <vcclr.h>  
// using namespace System;  
  
size_t getlen(System::String ^ s) {  
   // Since this is an outside string, we want to be secure.  
   // To be secure, we need a maximum size.  
   size_t maxsize = 256;  
   // make sure it doesn't move during the unmanaged call  
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);  
   return wcsnlen(pinchars, maxsize);  
};  
  
int main() {  
   System::Console::WriteLine(getlen("testing"));  
}  
```  
  
 **7**   
## Пример  
 Внутренний указатель имеет те же свойства, что и собственный указатель C\+\+.  Так, его можно использовать для выполнения обхода связанной структуры данных, а также выполнения вставки и удаления с помощью одного только указателя.  
  
```  
// PtrToStringChars_3.cpp  
// compile with: /clr /LD  
using namespace System;  
ref struct ListNode {  
   Int32 elem;   
   ListNode ^ Next;  
};  
  
void deleteNode( ListNode ^ list, Int32 e ) {   
   interior_ptr<ListNode ^> ptrToNext = &list;  
   while (*ptrToNext != nullptr) {  
      if ( (*ptrToNext) -> elem == e )  
         *ptrToNext = (*ptrToNext) -> Next;   // delete node  
      else  
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node  
   }  
}  
```  
  
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)