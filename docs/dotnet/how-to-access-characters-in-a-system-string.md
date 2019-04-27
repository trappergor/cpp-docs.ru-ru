---
title: Практическое руководство. Доступа к символам объекта System::String
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: 6b9e30a18ab1d2b8463ccccae0b265bc20904020
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222940"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Практическое руководство. Доступа к символам объекта System::String

Можно получить доступ к символов <xref:System.String> объекта для высокой производительности вызовов неуправляемых функций, принимающих `wchar_t*` строк. Метод возвращает внутренний указатель на первый символ <xref:System.String> объекта. Этот указатель можно работать напрямую или закрепленный и передается в функцию, ожидающую обычный `wchar_t` строка.

## <a name="example"></a>Пример

`PtrToStringChars` Возвращает <xref:System.Char>, который является внутренним указателем (также известный как `byref`). Таким образом это подвергаются сборке мусора. Закрепить этот указатель, если вы собираетесь передать его в неуправляемую функцию, не нужно.

Рассмотрим следующий код.  Закрепление не требуется, поскольку `ppchar` является внутренним указателем, и если сборщик мусора перемещает строки, он указывает, будет также обновить `ppchar`. Без [pin_ptr (C++выполняет)](../extensions/pin-ptr-cpp-cli.md), код будет работать, и не имеет потенциальных снижение производительности, вызванные путем закрепления.

Если передать `ppchar` в неуправляемую функцию, должен быть закрепляющий указатель; сборщик мусора не сможете обновить все указатели в кадре стека неуправляемый.

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

В данном примере демонстрируются там, где необходима закрепления.

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

Внутренний указатель имеет все свойства собственный указатель C++. Например можно использовать его связанной структуры данных и выполнения вставки и удаления с помощью только одного указателя:

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
