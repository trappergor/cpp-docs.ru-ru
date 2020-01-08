---
title: __int8, __int16, __int32, __int64
ms.date: 10/09/2018
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
- __int8
- __int16
- __int32
- __int64
- _int8
- _int16
- _int32
- _int64
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
ms.openlocfilehash: 4e793f23581f7dc62a39fcd8c5c504fb5a2ccbc9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301474"
---
# <a name="__int8-__int16-__int32-__int64"></a>__int8, __int16, __int32, __int64

**Блок, относящийся только к системам Майкрософт**

В Microsoft C/C++ поддерживаются целочисленные типы с указанием размера. Можно объявить 8-, 16-, 32-или 64-разрядные целочисленные переменные с помощью спецификатора типа **__int**<em>n</em> , где *n* — 8, 16, 32 или 64.

В следующем примере объявляется по одной переменной каждого из этих целочисленных типов с указанием размера:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Типы **__int8**, **__int16**и **__int32** являются синонимами для типов ANSI, имеющих одинаковый размер, и полезны для написания переносимого кода, который ведет себя одинаково на нескольких платформах. Тип данных **__int8** является синонимом типа **char**, **__int16** является синонимом типа **Short**, а **__int32** является синонимом типа **int**. Тип **__int64** является синонимом типа **Long**Long.

Для совместимости с предыдущими версиями **_int8**, **_int16**, **_int32**и **_int64** являются синонимами для **__int8**, **__int16**, **__int32**и **__int64** , если не задан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

## <a name="example"></a>Пример

В следующем примере показано, что параметр __int*XX* будет выдвинут на **int**:

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

## <a name="see-also"></a>См. также:

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Встроенные типы](../cpp/fundamental-types-cpp.md)<br/>
[Диапазоны типов данных](../cpp/data-type-ranges.md)<br/>
