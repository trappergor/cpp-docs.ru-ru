---
title: XMMWORD
ms.date: 08/30/2018
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 59d1ba71260ed08b761c332e887cf27517762303
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326346"
---
# <a name="xmmword"></a>XMMWORD

Используется для 128-разрядные операнды мультимедиа с инструкциями MMX и SSE (XMM).

## <a name="syntax"></a>Синтаксис

> XMMWORD

## <a name="remarks"></a>Примечания

`XMMWORD` представляет тот же тип, что [__m128](../../cpp/m128.md).

## <a name="example"></a>Пример

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```