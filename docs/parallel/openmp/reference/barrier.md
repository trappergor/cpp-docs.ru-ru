---
title: Барьер | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- barrier
dev_langs:
- C++
helpviewer_keywords:
- barrier OpenMP directive
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c220106d62bf65505c9c5b48085a9ee3e67fe0cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415035"
---
# <a name="barrier"></a>barrier

Синхронизирует все потоки в группе; все потоки остановиться барьера, пока все потоки выполнения барьера.

## <a name="syntax"></a>Синтаксис

```
#pragma omp barrier
```

## <a name="remarks"></a>Примечания

`barrier` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.6.3 директива barrier](../../../parallel/openmp/2-6-3-barrier-directive.md).

## <a name="example"></a>Пример

Пример использования `barrier`, см. в разделе [master](../../../parallel/openmp/reference/master.md).

## <a name="see-also"></a>См. также

[Директивы](../../../parallel/openmp/reference/openmp-directives.md)