---
title: 2.6.3 директива barrier | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68df92207feb45a77055098cdb1227a68b04bcab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689796"
---
# <a name="263-barrier-directive"></a>2.6.3 Директива barrier
**Барьера** директива синхронизирует все потоки в команде. При обнаружении, каждый поток в группе ожидает, пока все остальные достижение этой точки. Синтаксис **барьера** директивы таков:  
  
```  
#pragma omp barrier new-line  
```  
  
 После обнаружения всех потоков в группе барьера каждый поток в команде начинает выполняться инструкции после директивы барьера параллельно. Обратите внимание, что поскольку **барьера** директива не поддерживает инструкции языка C, как часть его синтаксис, существуют некоторые ограничения на его размещение в программе. В разделе [приложении C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) для формальная грамматика. В следующем примере иллюстрируется эти ограничения.  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```