---
title: XMMWORD
ms.date: 08/30/2018
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: a248c9318764cd632fed2afd8481ee2b2102fe31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479786"
---
# <a name="xmmword"></a>XMMWORD

Используется для 128-разрядные операнды мультимедиа с инструкциями MMX и SSE (XMM).

## <a name="syntax"></a>Синтаксис

> XMMWORD

## <a name="remarks"></a>Примечания

`XMMWORD` представляет тот же тип, что [__m128](../../cpp/m128.md).

## <a name="example"></a>Пример

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```