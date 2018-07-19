---
title: Класс mask_array | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::mask_array
dev_langs:
- C++
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1dc03a9d8f5f11b08ab2d5cb9d21190ac0a75925
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962677"
---
# <a name="maskarray-class"></a>Класс mask_array

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
