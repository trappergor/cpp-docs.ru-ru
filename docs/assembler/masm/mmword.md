---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: 1205338f9140c74a3a6e0b4bce57983edc80862e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541128"
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
    movq     mm0, mmword ptr [ebx]
```