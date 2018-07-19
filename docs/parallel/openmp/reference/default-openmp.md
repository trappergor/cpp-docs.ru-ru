---
title: по умолчанию (OpenMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fc39951270138e9bd243172b289e7bd96190f14
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692325"
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