---
title: .ALLOCSTACK
ms.date: 12/17/2019
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: bcc94619dfa24ab5c8b5d23a60825641290ef176
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75314189"
---
# <a name="allocstack"></a>.ALLOCSTACK

Создает **UWOP_ALLOC_SMALL** или **UWOP_ALLOC_LARGE** с указанным размером для текущего смещения в прологе.

## <a name="syntax"></a>Синтаксис

> **.**  *Размер* аллокстакк

## <a name="remarks"></a>Заметки

MASM выберет наиболее эффективную кодировку для заданного размера.

**. АЛЛОКСТАКК** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и допускается только в прологе, который расширяется из объявления кадра [процесса](proc.md) в [. ](dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. АЛЛОКСТАКК** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Операнд *размера* должен быть кратен 8.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Образец

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

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
