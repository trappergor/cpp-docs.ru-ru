---
title: Класс indirect_array
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 43c54bf3dae02eb117b15cae0dd7de9bb4a9db51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404998"
---
# <a name="indirectarray-class"></a>Класс indirect_array

Внутренний, вспомогательный класс шаблона, который поддерживает объекты, представляющие подмножества valarray, предоставляя операции между массивами подмножеств, заданных в виде подмножества индексов родительского valarray.

## <a name="syntax"></a>Синтаксис

## <a name="remarks"></a>Примечания

Этот класс описывает объект, который хранит ссылку на объект `va` класса [valarray](../standard-library/valarray-class.md)**\<тип >**, вместе с объектом `xa` класса `valarray<size_t>`, который описывает последовательность элементов для выбора из `valarray<Type>` объекта.

При создании `indirect_array<Type>` только путем написания выражения вида `va[xa]`. Функции-члены класса indirect_array затем ведут себя как соответствующие сигнатуры функций, заданные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов.

Последовательность состоит **xa.** [размер](../standard-library/valarray-class.md#size) элементов, где элемент `I` становится индексом **xa**[ `I`] в `va`.

## <a name="example"></a>Пример

```cpp
// indirect_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Вывод

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
