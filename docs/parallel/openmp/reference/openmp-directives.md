---
title: "Директивы OpenMP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e8d47e6376b3786b27305e65bdb55f0c292995d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-directives"></a>Директивы OpenMP
Ссылки на директивы использования в OpenMP API.  
  
 Visual C++ поддерживает следующие директивы OpenMP.  
  
|Директива|Описание:|  
|---------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|Указывает, что области памяти, которая будет обновляться автоматически.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|Синхронизирует все потоки в команде; все потоки приостановить в барьера, пока все потоки выполняют барьера.|  
|[critical](../../../parallel/openmp/reference/critical.md)|Указывает, что код выполняется только в одном потоке одновременно.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Указывает, что все потоки имеют одинаковое представление в памяти для всех общих объектов.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|В результаты работы вызывает для цикла внутри параллельной области, чтобы разделить между потоками.|  
|[master](../../../parallel/openmp/reference/master.md)|Указывает, что только master threadshould выполняться части программы.|  
|[упорядоченные](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Указывает, код под Параллелизованный цикл должен выполняться как последовательный цикл.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Определяет параллельной области, который является код, который будет выполняться несколько потоков параллельно.|  
|[Разделы](../../../parallel/openmp/reference/sections-openmp.md)|Определяет разделы кода, чтобы разделить между всеми потоками.|  
|[single](../../../parallel/openmp/reference/single.md)|Позволяет указать, что фрагмент кода должна выполняться в одном потоке, не обязательно главного потока.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Указывает, что переменная является закрытым в поток.|  
  
## <a name="see-also"></a>См. также  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)