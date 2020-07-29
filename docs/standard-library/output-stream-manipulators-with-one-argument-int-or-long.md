---
title: Манипуляторы потока вывода с одним аргументом (int или long)
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: 203797eef95e3dab0c079e35baefcea99c3b966d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217666"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Манипуляторы потока вывода с одним аргументом (int или long)

Библиотека классов iostream предоставляет набор макросов для создания параметризованных манипуляторов. **`int`** **`long`** Особым случаем являются манипуляторы с одним аргументом или. Чтобы создать манипулятор потока вывода, принимающий один **`int`** **`long`** аргумент или (например `setw` ,), необходимо использовать макрос _Smanip, который определен в \<iomanip> . В этом примере определяется манипулятор `fillblank`, который вставляет в поток заданное число пробелов.

## <a name="example"></a>Пример

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>См. также раздел

[Пользовательские манипуляторы с аргументами](../standard-library/custom-manipulators-with-arguments.md)
