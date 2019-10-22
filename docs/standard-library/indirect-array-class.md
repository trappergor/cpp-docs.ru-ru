---
title: Класс indirect_array
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 6be0c5153cbc94d09b414fc9e14fa498c7a4cfa7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687920"
---
# <a name="indirect_array-class"></a>Класс indirect_array

Внутренний, вспомогательный шаблон класса, который поддерживает объекты, являющиеся подмножествами объектов valarray, предоставляя операции между массивами подмножества, определенными путем указания подмножества индексов родительского valarray.

## <a name="syntax"></a>Синтаксис

## <a name="remarks"></a>Заметки

Класс описывает объект, хранящий ссылку на объект `va` класса [valarray](../standard-library/valarray-class.md)  **\<Type >** , а также объект `xa` класса `valarray<size_t>`, который описывает последовательность элементов для выбора из объекта `valarray<Type>`.

Объект `indirect_array<Type>` создается только путем написания выражения формы `va[xa]`. Функции-члены класса indirect_array ведут себя так же, как и соответствующие сигнатуры функций, определенные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов.

Последовательность состоит из **XA.** [Размер](../standard-library/valarray-class.md#size) элементов, где элемент `I` преобразуется в индекс **XA**[`I`] внутри `va`.

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
