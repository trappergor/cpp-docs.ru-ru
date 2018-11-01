---
title: Класс allocator_fixed_size
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
ms.openlocfilehash: d050a127fe3e62bf8f4eb4ce56fe25e33f88c041
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535890"
---
# <a name="allocatorfixedsize-class"></a>Класс allocator_fixed_size

Описывает объект, который управляет выделением и освобождением памяти для объектов типа *тип* использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_fixed_size](../standard-library/max-fixed-size-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Type*|Тип элементов, распределяемых распределителем.|

## <a name="remarks"></a>Примечания

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) макрос передает этот класс как *имя* параметр в следующей инструкции: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
