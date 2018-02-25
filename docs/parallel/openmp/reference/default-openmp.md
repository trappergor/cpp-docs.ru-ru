---
title: "по умолчанию (OpenMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca0a9cd39e6c9b2896a0435e1a9b0d503d59f9dd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="default-openmp"></a>default (OpenMP)
Задает поведение неограниченного переменных в параллельной области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>Примечания  
 `shared`, который фактически является Если `default` предложение не указано, означает, что любой переменной в параллельной области будут рассматриваться, как если бы он был указан с [общего](../../../parallel/openmp/reference/shared-openmp.md) предложения. `none` означает, что все переменные, используемые в параллельной области, не ограничены областью с [закрытый](../../../parallel/openmp/reference/private-openmp.md), [общего](../../../parallel/openmp/reference/shared-openmp.md), [сокращения](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), или [lastprivate](../../../parallel/openmp/reference/lastprivate.md) предложение приведет к ошибке компилятора.  
  
 `default` применяется к следующие директивы:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.5 по умолчанию](../../../parallel/openmp/2-7-2-5-default.md).  
  
## <a name="example"></a>Пример  
 В разделе [закрытый](../../../parallel/openmp/reference/private-openmp.md) пример использования `default`.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)