---
title: Директивы OpenMP | Документация Майкрософт
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
ms.openlocfilehash: 983a71920e9e7ce390ab8c64e81886db0d459450
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389452"
---
# <a name="openmp-directives"></a>Директивы OpenMP

Ссылки на директивы, используемые в OpenMP API.

Visual C++ поддерживает следующие директивы OpenMP.

|Директива|Описание|
|---------------|-----------------|
|[atomic](../../../parallel/openmp/reference/atomic.md)|Указывает, что ячейку памяти, которая обновляется атомарно.|
|[barrier](../../../parallel/openmp/reference/barrier.md)|Синхронизирует все потоки в группе; все потоки остановиться барьера, пока все потоки выполнения барьера.|
|[critical](../../../parallel/openmp/reference/critical.md)|Указывает, что код только выполняется в одном потоке за раз.|
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Указывает, что все потоки имеют одинаковое представление памяти для всех общих объектов.|
|[for](../../../parallel/openmp/reference/for-openmp.md)|Приводит к работе, выполненной в цикл внутри параллельной области для будет разделен между потоками.|
|[master](../../../parallel/openmp/reference/master.md)|Указывает, что только master threadshould выполняться части программы.|
|[Упорядоченные](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Указывает этот код в разделе Параллелизованный цикл должен выполняться как последовательный цикл.|
|[parallel](../../../parallel/openmp/reference/parallel.md)|Определяет параллельной области, который приведен код, который будет выполняться сразу несколько потоков параллельно.|
|[Разделы](../../../parallel/openmp/reference/sections-openmp.md)|Идентифицирует разделов кода необходимо распределить между всеми потоками.|
|[single](../../../parallel/openmp/reference/single.md)|Позволяет указать, что раздела кода, должна выполняться в одном потоке, не обязательно главного потока.|
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Указывает, что переменная является частной для потока.|

## <a name="see-also"></a>См. также

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[Предложения](../../../parallel/openmp/reference/openmp-clauses.md)