---
title: omp_unset_nest_lock | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_nest_lock OpenMP function
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8434fb3e4cb07b11f2142f78ee4b243e6945dfd9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691668"
---
# <a name="ompunsetnestlock"></a>omp_unset_nest_lock
Освобождение блокировки, которая.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void omp_unset_nest_lock(   
   omp_nest_lock_t *lock   
);  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `lock`  
 Переменная типа [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , инициализированный с [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md), принадлежащие потоком и выполняется в функции.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [3.2.4 функции omp_unset_lock и omp_unset_nest_lock](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).  
  
## <a name="example"></a>Пример  
 В разделе [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) пример использования `omp_unset_nest_lock`.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)