---
title: Целочисленные типы размеров C
ms.date: 07/22/2020
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
ms.openlocfilehash: 7f785efb2fc93d2ec57783dd20a43642c87e4a4c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226507"
---
# <a name="c-sized-integer-types"></a>Целочисленные типы размеров C

**Блок, относящийся только к системам Microsoft**

В Microsoft C поддерживаются целочисленные типы с указанием размера. Это позволяет объявлять 8-, 16-, 32- и 64-разрядные целочисленные переменные при помощи описателя типа `__intN` (где *`N`* означает размер целочисленной переменной в битах). Таким образом, *n* может иметь значение 8, 16, 32 или 64. В следующем примере объявляется по одной переменной каждого из 4 целочисленных типов с указанием размера:

```C
__int8  nSmall;     // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Первые три целочисленных типа с указанием размера являются аналогами типов ANSI, имеющих такой же размер. Они полезны для написания переносимого кода, который одинаково выполняется на различных платформах. Тип данных **`__int8`** аналогичен типу **`char`** , **`__int16`**  — типу **`short`** , **`__int32`**  — типу **`int`** , а **`__int64`**  — типу **`long long`** .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Хранение базовых типов](../c-language/storage-of-basic-types.md)
