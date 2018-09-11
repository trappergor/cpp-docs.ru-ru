---
title: XMMWORD. | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- XMMWORD
dev_langs:
- C++
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fbb578c5e168f53bc1b4e217713efa1ea329743
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689218"
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