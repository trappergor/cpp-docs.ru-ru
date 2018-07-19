---
title: omp_set_nest_lock | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e49a63fc4bc8d31583478ee6f61fe7b374bb9f0b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691018"
---
# <a name="ompsetnestlock"></a>omp_set_nest_lock
Блоки потоков выполнения, пока блокировка не освободится.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void omp_set_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `lock`  
 Переменная типа [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , инициализированный с [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [3.2.3 функции omp_set_lock и omp_set_nest_lock](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).  
  
## <a name="examples"></a>Примеры  
 В разделе [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) пример использования `omp_set_nest_lock`.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)