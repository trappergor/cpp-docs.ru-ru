---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: d4378c1435df09f249fe7f55dabd4bd0f43f6100
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397179"
---
# <a name="mmword"></a>MMWORD

Используется для 64-разрядных операндов мультимедиа с инструкциями MMX и SSE (XMM).

## <a name="syntax"></a>Синтаксис

> **MMWORD**

## <a name="remarks"></a>Примечания

**Ммворд** — это тип.  До **ммворд** , добавленного в MASM, эквивалентные функции могут быть достигнуты с помощью:

```asm
    mov mm0, qword ptr [ebx]
```

Хотя обе инструкции работают с 64-разрядными операндами, **QWORD** является типом для 64-разрядных целых чисел без знака, а **ммворд** — типом для значения 64-bit.

**Ммворд** предназначен для представления того же типа, что и [__m64](../../cpp/m64.md).

## <a name="example"></a>Пример

```asm
    movq     mm0, mmword ptr [ebx]
```
