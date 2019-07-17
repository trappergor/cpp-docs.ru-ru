---
title: '&lt;memory_resource&gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: b5957412d2beff0dc709dc71a77834f13eeacb41
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269346"
---
# <a name="ltmemoryresourcegt"></a>&lt;memory_resource&gt;

Определяет memory_resource класс шаблона контейнера и его вспомогательные шаблоны.

## <a name="syntax"></a>Синтаксис

```cpp
#include <memory_resource>
```

## <a name="members"></a>Участники

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator!=](../standard-library/memory-resource-operators.md#op_neq)|Проверяет объект memory_resource слева от оператора не равен объекту memory_resource справа от оператора.|
|[operator==](../standard-library/memory-resource-operators.md#op_eq_eq)|Проверяет объект memory_resource слева от оператора равен объекту memory_resource справа от оператора.|

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
|[pool_options структуры](../standard-library/pool-options-structure.md)||
|[Класс synchronized_pool_resource](../standard-library/synchronized-pool-resource-class.md)||
|[Класс unsynchronized_pool_resource](../standard-library/unsynchronized-pool-resource-class.md)||

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
