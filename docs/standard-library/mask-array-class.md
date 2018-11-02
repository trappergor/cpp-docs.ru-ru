---
title: mask_array - класс
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 108c942bef33e44b515d46e953c9d99274e3ce8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475829"
---
# <a name="maskarray-class"></a>mask_array - класс

Внутренний, вспомогательный класс шаблона, который поддерживает объекты, представляющие подмножества родительских valarray, указанных логическим выражением, предоставляя операции между массивами подмножеств.

## <a name="syntax"></a>Синтаксис

## <a name="remarks"></a>Примечания

Этот класс описывает объект, который хранит ссылку на объект `va` класса [valarray](../standard-library/valarray-class.md)**\<тип >**, вместе с объектом `ba` класса [ valarray\<bool >](../standard-library/valarray-bool-class.md), который описывает последовательность элементов для выбора из `valarray<Type>` объекта.

При создании `mask_array<Type>` только путем написания выражения вида [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at). Функции-члены класса mask_array ведут себя как соответствующие сигнатуры функций, заданные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов.

Последовательность состоит максимум `ba.size` элементов. Элемент *J* включается, только если **ba**[ *J*] имеет значение true. Таким образом, существует столько элементов в последовательности существует элементов со значением true в `ba`. Если `I` является индексом наименьшего элемента true в `ba`, затем **va**[ `I`] является нулевым элементом в выбранной последовательности.

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

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
