---
title: '&lt;memory_resource &gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: 752396bb06b292ce29b7c6cd292287955b6066a7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687710"
---
# <a name="ltmemory_resourcegt"></a>&lt;memory_resource &gt;

Определяет шаблон класса контейнера memory_resource и его вспомогательные шаблоны.

## <a name="syntax"></a>Синтаксис

```cpp
#include <memory_resource>
```

## <a name="members"></a>Члены

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор!= ](../standard-library/memory-resource-operators.md#op_neq)|Проверяет, не равен ли объект memory_resource слева от оператора объекту memory_resource в правой части.|
|[оператор==](../standard-library/memory-resource-operators.md#op_eq_eq)|Проверяет, равен ли объект memory_resource слева от оператора объекту memory_resource в правой части.|

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
