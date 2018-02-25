---
title: "copyin | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae680b2af468b9b11a7d2de44966ad554eec0150
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="copyin"></a>copyin
Позволяет потокам для доступа к значению главного потока для [threadprivate](../../../parallel/openmp/reference/threadprivate.md) переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 `threadprivate` Переменную, которая будет инициализироваться со значением переменной в главного потока, которое существовало до параллельной конструкции.  
  
## <a name="remarks"></a>Примечания  
 `copyin` применяется к следующие директивы:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Пример  
 В разделе [threadprivate](../../../parallel/openmp/reference/threadprivate.md) пример использования `copyin`.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)