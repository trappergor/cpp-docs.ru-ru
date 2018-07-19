---
title: Пространство имен Concurrency константы (AMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::HLSL_MAX_NUM_BUFFERS
- amp/Concurrency::MODULENAME_MAX_LENGTH
dev_langs:
- C++
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: adc9aefd059be2932b6903f5c33ada05305d9ed1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695854"
---
# <a name="concurrency-namespace-constants-amp"></a>Пространство имен Concurrency константы (AMP)
|||  
|-|-|  
|[HLSL_MAX_NUM_BUFFERS](#hlsl_max_num_buffers)|[MODULENAME_MAX_LENGTH](#modulename_max_length)|  
  
##  <a name="hlsl_max_num_buffers"></a>  Константа HLSL_MAX_NUM_BUFFERS  
 Максимальное количество буферов, допустимых в DirectX.  
  
```  
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;  
```  
  
##  <a name="modulename_max_length"></a>  Константа MODULENAME_MAX_LENGTH  
 Хранит Максимальная длина имени модуля. Это значение должно быть одинаковым на компилятор и среда выполнения.  
  
```  
static const UINT MODULENAME_MAX_LENGTH = 1024;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
