---
title: Константы пространства имен Concurrency (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::HLSL_MAX_NUM_BUFFERS
- amp/Concurrency::MODULENAME_MAX_LENGTH
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
ms.openlocfilehash: 512c0e30048584ae97a5da14fd5b3304f6888390
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841224"
---
# <a name="concurrency-namespace-constants-amp"></a>Константы пространства имен Concurrency (AMP)

[HLSL_MAX_NUM_BUFFERS](#hlsl_max_num_buffers)\
[MODULENAME_MAX_LENGTH](#modulename_max_length)

## <a name="hlsl_max_num_buffers-constant"></a><a name="hlsl_max_num_buffers"></a> Константа HLSL_MAX_NUM_BUFFERS

Максимальное число буферов, разрешенных DirectX.

```cpp
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;
```

## <a name="modulename_max_length-constant"></a><a name="modulename_max_length"></a> Константа MODULENAME_MAX_LENGTH

Сохраняет максимальную длину имени модуля. Это значение должно быть одинаковым в компиляторе и во время выполнения.

```cpp
static const UINT MODULENAME_MAX_LENGTH = 1024;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
