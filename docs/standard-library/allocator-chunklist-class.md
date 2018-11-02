---
title: Класс allocator_chunklist
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
helpviewer_keywords:
- stdext::allocator_chunklist
- stdext::allocators [C++], allocator_chunklist
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
ms.openlocfilehash: d52eeb1f34938958c9716692ed6bbd7d830c93b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630494"
---
# <a name="allocatorchunklist-class"></a>Класс allocator_chunklist

Описывает объект, который управляет выделением и освобождением памяти для объектов, использующих кэш типа [cache_chunklist](../standard-library/cache-chunklist-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_chunklist;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Type*|Тип элементов, распределяемых распределителем.|

## <a name="remarks"></a>Примечания

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) макрос передает этот класс как *имя* параметр в следующей инструкции: `ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist);`

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
