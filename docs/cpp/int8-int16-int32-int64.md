---
title: "__int8, __int16, __int32, __int64 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __int8_cpp
- __int64
- __int8
- __int16
- __int16_cpp
- __int64_cpp
- __int32_cpp
- __int32
dev_langs:
- C++
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type, integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 82b06a776d40121b5f147388dadf053b5b072659
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 В Microsoft C/C++ поддерживаются целочисленные типы с указанием размера. 8-, 16-, 32- или 64-разрядные целочисленные переменные можно объявить с помощью **__int** * n * спецификатор, где * n * 8, 16, 32 или 64.  
  
 В следующем примере объявляется по одной переменной каждого из этих целочисленных типов с указанием размера:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Типы `__int8`, `__int16` и `__int32` аналогичны типам данных ANSI с таким же размером. Они могут использоваться для написания переносимого кода, который одинаково работает на разных платформах. `__int8` Тип данных является синонимом типа `char`, `__int16` является синонимом типа **короткие**, и `__int32` является синонимом типа `int`. Тип `__int64` не имеет эквивалента в ANSI.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, что __int*xx* параметр будет повышен до `int`:  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
```Output  
func  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Базовые типы](../cpp/fundamental-types-cpp.md)   
 [Диапазоны типов данных](../cpp/data-type-ranges.md)
