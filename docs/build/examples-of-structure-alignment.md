---
title: Примеры выравнивания структуры
ms.date: 11/19/2018
helpviewer_keywords:
- structure alignment
- examples [C++], structure alignment
ms.assetid: 03d137bf-5cc4-472e-9583-6498f2534199
ms.openlocfilehash: 7c4b3ae29674e9c4fc27e8e175867339001b9a0d
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175344"
---
# <a name="examples-of-structure-alignment"></a>Примеры выравнивания структуры

Следующие четыре примера каждого объявите выровненные структуры или объединения и соответствующих показателей проиллюстрировать макет структуры или объединения в памяти. Каждый столбец на рисунке представляет байт памяти, а число в столбце указывает смещение, байтов. Имя во второй строке каждом рисунке соответствует имени переменной в объявлении. Затененные столбцы определяют заполнение, необходимое для достижения указанное выравнивание.

## <a name="example-1"></a>Пример 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![Пример 1. Структура AMD преобразование макета](../build/media/vcamd_conv_ex_1_block.png "структуре пример 1 преобразования AMD")

## <a name="example-2"></a>Пример 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![Пример 2 структура AMD преобразование макета](../build/media/vcamd_conv_ex_2_block.png "структуре пример 2 преобразования AMD")

## <a name="example-3"></a>Пример 3

```C
// Total size = 22 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![Пример 2 структура AMD преобразование макета](../build/media/vcamd_conv_ex_3_block.png "структуре пример 2 преобразования AMD")

## <a name="example-4"></a>Пример 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![Layouit объединения 4 пример преобразования AMD](../build/media/vcamd_conv_ex_4_block.png "layouit объединения 4 пример преобразования AMD")

## <a name="see-also"></a>См. также

[Типы и хранилище](../build/types-and-storage.md)<br/>
