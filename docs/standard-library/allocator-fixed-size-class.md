---
title: Класс allocator_fixed_size | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc1b13fefbb48ebd28b27f87e0a5622fd3cd5ec4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="allocatorfixedsize-class"></a>Класс allocator_fixed_size

Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_fixed_size](../standard-library/max-fixed-size-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`Type`|Тип элементов, распределяемых распределителем.|

## <a name="remarks"></a>Примечания

Макрос [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) передает этот класс как параметр `name` в следующей инструкции: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
