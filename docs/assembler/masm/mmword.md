---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: e4ebaa9d47a569bc9cf7d843d3ddb54ca5d713a0
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328231"
---
# <a name="mmword"></a>MMWORD

Используется для 64-разрядные операнды мультимедиа с инструкциями MMX и SSE (XMM).

## <a name="syntax"></a>Синтаксис

> MMWORD

## <a name="remarks"></a>Примечания

`MMWORD` — Это тип.  До MMWORD, добавляемый MASM удалось добиться аналогичных функциональных возможностей с:

```asm
    mov mm0, qword ptr [ebx]
```

Хотя обе инструкции работать на 64-разрядных операндов, `QWORD` является типом для 64-разрядных целых беззнаковых чисел и `MMWORD` является типом для 64-разрядное значение мультимедиа.

`MMWORD` представляет тот же тип, что [__m64](../../cpp/m64.md).

## <a name="example"></a>Пример

```asm
    movq     mm0, mmword ptr [ebx]
```