---
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: fd3b9f40b7ff9fa4dae570e0ed906c13a9456424
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75311927"
---
# <a name="mmword"></a>MMWORD

Используется для 64-разрядных операндов мультимедиа с инструкциями MMX и SSE (XMM).

## <a name="syntax"></a>Синтаксис

> **MMWORD**

## <a name="remarks"></a>Заметки

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

## <a name="see-also"></a>См. также раздел

[Грамматика MASM BNF](masm-bnf-grammar.md)
