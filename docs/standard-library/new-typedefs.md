---
title: Определения типов &lt;new&gt;
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 30bd84a1d69d3d8f24cd36450a18b23b92c3c2c6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076425"
---
# <a name="ltnewgt-typedefs"></a>Определения типов &lt;new&gt;

## <a name="hardware_constructive_interference_size"></a><a name="hardware_constructive_interference_size"></a>hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Примечания

Это число является максимальным рекомендуемым размером непрерывной памяти, занимаемой двумя объектами, к которым осуществляется доступ с использованием временных расположений параллельных потоков. Он должен быть не менее `alignof(max_align_t)`.

### <a name="example"></a>Пример

```cpp
struct together {
    atomic<int> dog;
    int puppy;
};

struct kennel {
    // Other data members...
    alignas(sizeof(together)) together pack;
    // Other data members...
};

static_assert(sizeof(together) <= hardware_constructive_interference_size);
```

## <a name="hardware_destructive_interference_size"></a><a name="hardware_destructive_interference_size"></a>hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Примечания

Это число является минимальным рекомендуемым смещением между двумя параллельно доступными объектами во избежание дополнительного снижения производительности из-за конкуренции, представленной реализацией. Он должен быть не менее `alignof(max_align_t)`.

### <a name="example"></a>Пример

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a><a name="new_handler"></a>new_handler

Тип указывает на функцию, подходящую для использования в качестве нового обработчика.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Примечания

Этот тип функции обработчика вызывается **оператором new** или `operator new[]`, когда они не могут удовлетворить запрос на дополнительное хранилище.

### <a name="example"></a>Пример

См. [set_new_handler](../standard-library/new-functions.md#set_new_handler) с примером использования `new_handler` в качестве как возвращаемого значения.
