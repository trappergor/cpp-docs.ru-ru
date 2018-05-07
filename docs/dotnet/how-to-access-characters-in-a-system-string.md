---
title: 'Как: доступ к символам объекта System::String | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ed9682492eedc915919758d42d5594560cb4a83a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Практическое руководство. Доступ к символам объекта System::String
Можно получить доступ к символов <xref:System.String> объекта для высокопроизводительных вызовов неуправляемых функций, принимающих `wchar_t*` строки. Метод возвращает внутренний указатель на первый символ <xref:System.String> объекта. Этот указатель можно работать напрямую или закрепленные и передается в функцию, ожидающую обычных `wchar_t` строки.  
  
## <a name="example"></a>Пример  
 `PtrToStringChars` Возвращает <xref:System.Char>, который является внутренним указателем (также известный как `byref`). Таким образом рекомендуется подвергаются сборке мусора. Не нужно закрепить этот указатель, только если необходимо передать его собственной функции.  
  
 Рассмотрим следующий код.  Закрепление не требуется, поскольку `ppchar` является внутренним указателем, и если сборщик мусора перемещение строки, он указывает, будет также обновление `ppchar`. Без [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md), код будет работать, и не иметь потенциальные снижение производительности, вызванные путем закрепления.  
  
 Если передать `ppchar` собственной функции, должен быть закрепляющий указатель; сборщик мусора не сможете обновить все указатели в кадре стека неуправляемым.  
  
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
  
```Output  
abcdefg  
```  
  
## <a name="example"></a>Пример  
 В этом примере представлены там, где необходима закрепления.  
  
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
  
```Output  
7  
```  
  
## <a name="example"></a>Пример  
 Внутренний указатель имеет те же свойства собственного указателя C++. Например его можно использовать для обхода связанной структуры данных и выполнять операции вставки и удаления с помощью только одного указателя:  
  
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
  
## <a name="see-also"></a>См. также  
 [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)