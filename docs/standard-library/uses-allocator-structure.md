---
title: Структура uses_allocator | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::uses_allocator
dev_langs:
- C++
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f46512279273ad8f85be23edd172345c896a4401
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855631"
---
# <a name="usesallocator-structure"></a>Структура uses_allocator

Специализации, которые всегда содержат значение true.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty, class Alloc>
struct uses_allocator<promise<Ty>, Alloc> : true_type;
template <class Ty, class Alloc>
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;
```

## <a name="requirements"></a>Требования

**Заголовок:** \<будущих >

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
