---
title: .PUSHREG
ms.date: 12/16/2019
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: de6ffd3668f47732144e8c632410f6dfde6b2f31
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318297"
---
# <a name="pushreg"></a>.PUSHREG

Создает `UWOP_PUSH_NONVOL` запись кода очистки для указанного номера регистра, используя текущее смещение в прологе.

## <a name="syntax"></a>Синтаксис

> . ПУШРЕГ *регистр*

## <a name="remarks"></a>Заметки

**. ПУШРЕГ** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и может использоваться только в прологе, который расширяется из объявления кадра [процесса](proc.md) в [. ](dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. ПУШРЕГ** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

*регистр* может быть одним из следующих: \
RAX | РККС | RDX | РБКС | RDI | РСИ | РБП | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Образец

### <a name="description"></a>Описание

В следующем примере показано, как отправлять непостоянные регистры.

### <a name="code"></a>Код

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
