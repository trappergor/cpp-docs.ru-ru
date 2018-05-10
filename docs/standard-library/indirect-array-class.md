---
title: Класс indirect_array | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::indirect_array
dev_langs:
- C++
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f1d24fb90b99d7b757f628be4b39d42f0c0051f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="indirectarray-class"></a>Класс indirect_array

Внутренний, вспомогательный класс шаблона, который поддерживает объекты, представляющие подмножества valarray, предоставляя операции между массивами подмножеств, заданных в виде подмножества индексов родительского valarray.

## <a name="syntax"></a>Синтаксис

## <a name="remarks"></a>Примечания

В классе описывается объект, который хранит ссылку на объект **va** класса [valarray](../standard-library/valarray-class.md)**\<Type>**, а также объект **xa** класса **valarray<size_t>**, который описывает порядок элементов для выбора из объекта **valarray\<Type>**.

Объект **indirect_array\<Type>** создается только путем написания выражения вида **va[xa]**. Функции — члены класса indirect_array затем ведут себя как соответствующие сигнатуры функций, определенных для **valarray\<Type>** с той разницей, что затрагивается только последовательность выбранных элементов.

Последовательность состоит из элементов **xa.**[size](../standard-library/valarray-class.md#size), где элемент `I` становится индексом **xa**[`I`] в **va**.

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
