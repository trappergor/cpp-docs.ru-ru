---
title: Класс indirect_array
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 5db5f2ce60038267b70ae8e77d9dd929d972af6a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456330"
---
# <a name="indirectarray-class"></a>Класс indirect_array

Внутренний, вспомогательный класс шаблона, который поддерживает объекты, представляющие подмножества valarray, предоставляя операции между массивами подмножеств, заданных в виде подмножества индексов родительского valarray.

## <a name="syntax"></a>Синтаксис

## <a name="remarks"></a>Примечания

Класс описывает объект, хранящий ссылку на `va` объект класса [valarray](../standard-library/valarray-class.md) **\<Type >** , вместе с объектом `xa` класса `valarray<size_t>`, который описывает последовательность элементов для выбора из `valarray<Type>` объект.

`indirect_array<Type>` Объект создается только путем написания выражения формы `va[xa]`. Функции-члены класса indirect_array ведут себя так же, как и соответствующие сигнатуры `valarray<Type>`функций, определенные для, за исключением того, что затрагивается только последовательность выбранных элементов.

Последовательность состоит из **XA.** [Размер](../standard-library/valarray-class.md#size) элементов, элемент `I` WHERE преобразуется в индекс **XA**[ `I`] в. `va`

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

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
