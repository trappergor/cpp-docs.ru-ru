---
title: __int8, __int16, __int32, __int64 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 723724a477a5cdb714aa2644e1db938d67fb7b73
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194255"
---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64

**Блок, относящийся только к системам Microsoft**

В Microsoft C/C++ поддерживаются целочисленные типы с указанием размера. Это можно объявлять 8-, 16-, 32- или 64-разрядные целочисленные переменные при помощи **__int**<em>n</em> описатель типа где *n* 8, 16, 32 или 64.

В следующем примере объявляется по одной переменной каждого из этих целочисленных типов с указанием размера:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Типы **__int8**, **__int16**, и **__int32** аналогичны типам данных ANSI с таким же размера и полезны для написания переносимого кода, который одинаково работает на различных платформах. **__Int8** тип данных является синонимом типа **char**, **__int16** является синонимом типа **короткие**, и **__int32**  является синонимом типа **int**. **__Int64** тип является синонимом типа **long long**.

## <a name="example"></a>Пример

Следующий пример показывает, что __int*xx* параметр будет повышен до **int**:

```cpp
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

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Фундаментальные типы](../cpp/fundamental-types-cpp.md)<br/>
[Диапазоны типов данных](../cpp/data-type-ranges.md)<br/>
