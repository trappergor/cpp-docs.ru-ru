---
title: Директивы OpenMP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7421f397b39c6d26c2e60042b25f37277afa5fd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692198"
---
# <a name="openmp-directives"></a>Директивы OpenMP
Ссылки на директивы использования в OpenMP API.  
  
 Visual C++ поддерживает следующие директивы OpenMP.  
  
|Директива|Описание|  
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