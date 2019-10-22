---
title: mask_array - класс
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 12398203d61f2c3ea155b5f6e6e7b118d4a13c75
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689406"
---
# <a name="mask_array-class"></a>mask_array - класс

Внутренний, вспомогательный шаблон класса, который поддерживает объекты, являющиеся подмножествами родительских объектов valarray, заданные с помощью логического выражения, предоставляя операции между массивами подмножества.

## <a name="syntax"></a>Синтаксис

## <a name="remarks"></a>Заметки

Класс описывает объект, хранящий ссылку на объект `va` класса [valarray](../standard-library/valarray-class.md)  **\<Type >** , а также объект `ba` класса [valarray \<bool >](../standard-library/valarray-bool-class.md), который описывает последовательность элементов для выбора. из объекта `valarray<Type>`.

Объект `mask_array<Type>` создается только путем написания выражения формы No [&#91;Ба&#93;](../standard-library/valarray-class.md#op_at). Функции-члены класса mask_array ведут себя так же, как и соответствующие сигнатуры функций, определенные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов.

Последовательность состоит не более `ba.size` элементов. Элемент *J* включается, только если **ba**[ *J*] имеет значение true. Таким образом, в последовательности содержится столько элементов, сколько в `ba` есть элементы. Если `I` является индексом самого нижнего истинного элемента в `ba`, то в выбранной последовательности значение **a [`I`** ] равно нулю.

## <a name="example"></a>Пример

```cpp
// mask_array.cpp
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

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Вывод

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
