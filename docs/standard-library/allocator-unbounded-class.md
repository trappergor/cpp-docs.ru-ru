---
title: Класс allocator_unbounded | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
dev_langs:
- C++
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 321737f62d0e2506ef6582f80bed7f398ad5977b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959915"
---
# <a name="allocatorunbounded-class"></a>Класс allocator_unbounded

Описывает объект, который управляет выделением и освобождением памяти для объектов типа *тип* использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_unbounded](../standard-library/max-unbounded-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Тип*|Тип элементов, распределяемых распределителем.|

## <a name="remarks"></a>Примечания

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) макрос передает этот класс как *имя* параметр в следующей инструкции: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
