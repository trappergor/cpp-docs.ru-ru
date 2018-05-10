---
title: lastprivate | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5aaf80e3061877c42154ab9ee5ccd30f47f17135
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="lastprivate"></a>lastprivate
Указывает, что версия контекст внешней переменной приравнивается к закрытой версии поток выполняет последней итерации (конструкция цикла for) или последний раздел (#pragma разделов).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 Переменная, которая задана равной закрытой версии поток выполняет последней итерации (конструкция цикла for) или последний раздел (#pragma разделов).  
  
## <a name="remarks"></a>Примечания  
 `lastprivate` применяется к следующие директивы:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Пример  
 В разделе [расписания](../../../parallel/openmp/reference/schedule.md) пример использования `lastprivate` предложения.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)