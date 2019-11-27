---
title: .ALLOCSTACK
ms.date: 08/30/2018
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: 6d9d86371503992d1bebe738fb6e6773581b10e3
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398634"
---
# <a name="allocstack"></a>.ALLOCSTACK

Создает **UWOP_ALLOC_SMALL** или **UWOP_ALLOC_LARGE** с указанным размером для текущего смещения в прологе.

## <a name="syntax"></a>Синтаксис

> **.**  *Размер* аллокстакк

## <a name="remarks"></a>Примечания

MASM выберет наиболее эффективную кодировку для заданного размера.

**. АЛЛОКСТАКК** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и допускается только в прологе, который расширяется из объявления кадра [процесса](../../assembler/masm/proc.md) в [. ](../../assembler/masm/dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. АЛЛОКСТАКК** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Операнд *размера* должен быть кратен 8.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Пример

В следующем примере показано, как задать обработчик очистки и исключения.

```asm
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console
text SEGMENT
PUBLIC Example3
PUBLIC Example3_UW
Example3_UW PROC NEAR
   ; exception/unwind handler body

   ret 0

Example3_UW ENDP

Example3 PROC FRAME : Example3_UW

   sub rsp, 16
.allocstack 16

.endprolog

   ; function body
    add rsp, 16
   ret 0

Example3 ENDP
text ENDS
END
```

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
