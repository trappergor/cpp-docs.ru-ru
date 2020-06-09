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
ms.openlocfilehash: c2342d068293714871b3f79675dd0d0b9db83448
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617547"
---
# <a name="allocator_chunklist-class"></a>Класс allocator_chunklist

Описывает объект, который управляет выделением и освобождением памяти для объектов, использующих кэш типа [cache_chunklist](cache-chunklist-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_chunklist;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Type*|Тип элементов, распределяемых распределителем.|

## <a name="remarks"></a>Комментарии

Макрос [ALLOCATOR_DECL](allocators-functions.md#allocator_decl) передает этот класс в качестве параметра *Name* в следующей инструкции:`ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist);`

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также раздел

[\<allocators>](allocators-header.md)
