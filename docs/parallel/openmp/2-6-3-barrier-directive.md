---
title: "2.6.3 директива barrier | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9c64787d9c6cc2dd0809f75f8f9db9819174d0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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