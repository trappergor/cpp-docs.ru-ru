---
title: '&lt;memory_resource&gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: d4b25c6ee575191f1e17b0202d33298e2e9e67f0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451904"
---
# <a name="ltmemoryresourcegt"></a>&lt;memory_resource&gt;

Определяет класс шаблона контейнера memory_resource и его вспомогательные шаблоны.

## <a name="syntax"></a>Синтаксис

```cpp
#include <memory_resource>
```

## <a name="members"></a>Участники

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator!=](../standard-library/memory-resource-operators.md#op_neq)|Проверяет, не равен ли объект memory_resource слева от оператора объекту memory_resource в правой части.|
|[operator==](../standard-library/memory-resource-operators.md#op_eq_eq)|Проверяет, равен ли объект memory_resource слева от оператора объекту memory_resource в правой части.|

### <a name="specialized-template-functions"></a>Специализированные функции шаблонов

|||
|-|-|
|[polymorphic_allocator](../standard-library/memory-resource-functions.md#poly_alloc)||

### <a name="functions"></a>Функции

|||
|-|-|
|[get_default_resource](../standard-library/memory-resource-functions.md#get_default)||
|[new_delete_resource](../standard-library/memory-resource-functions.md#new_delete)||
|[null_memory_resource](../standard-library/memory-resource-functions.md#null_memory)||
|[set_default_resource](../standard-library/memory-resource-functions.md#set_default)||

### <a name="classes-and-structs"></a>Классы и структуры

|||
|-|-|
|[Класс memory_resource](../standard-library/memory-resource-class.md)||
|[Класс monotonic_buffer_resource](../standard-library/monotonic-buffer-resource-class.md)||
|[Структура pool_options](../standard-library/pool-options-structure.md)||
|[Класс synchronized_pool_resource](../standard-library/synchronized-pool-resource-class.md)||
|[Класс unsynchronized_pool_resource](../standard-library/unsynchronized-pool-resource-class.md)||

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
