---
title: MMWORD. | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7314c6d0861195e312c7f72481d2e195e041965d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679238"
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