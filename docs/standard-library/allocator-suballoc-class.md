---
title: Класс allocator_suballoc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
dev_langs:
- C++
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6238aeada530a8fc33fc98b79cba969353796ae
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953092"
---
# <a name="allocatorsuballoc-class"></a>Класс allocator_suballoc

Описывает объект, который управляет выделением и освобождением памяти для объектов типа *тип* использующих кэш типа [cache_suballoc](../standard-library/cache-suballoc-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Тип*|Тип элементов, распределяемых распределителем.|

## <a name="remarks"></a>Примечания

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) макрос передает этот класс как *имя* параметр в следующей инструкции: `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
