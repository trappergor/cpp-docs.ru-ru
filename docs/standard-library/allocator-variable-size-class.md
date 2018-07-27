---
title: Класс allocator_variable_size | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46ba5742f6beb308ada7ed64788577768afeac60
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953105"
---
# <a name="allocatorvariablesize-class"></a>Класс allocator_variable_size

Описывает объект, который управляет выделением и освобождением памяти для объектов типа *тип* использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_variable_size](../standard-library/max-variable-size-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_variable_size;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Тип*|Тип элементов, распределяемых распределителем.|

## <a name="remarks"></a>Примечания

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) макрос передает этот класс как *имя* параметр в следующей инструкции: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
