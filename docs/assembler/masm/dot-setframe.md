---
title: .SETFRAME
ms.date: 12/17/2019
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: 8c491a811634995398a37aa001cc1c93f8434114
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318245"
---
# <a name="setframe"></a>.SETFRAME

Заполняет поле регистра кадра и смещение в данных очистки, используя указанный регистр (*reg*) и смещение (*смещение*). Смещение должно быть кратным 16 и меньше или равно 240. Эта директива также создает `UWOP_SET_FPREG` запись кода очистки для указанного регистра, используя текущее смещение пролога.

## <a name="syntax"></a>Синтаксис

> **. СЕТФРАМЕ** *reg*, *смещение*

## <a name="remarks"></a>Заметки

**. СЕТФРАМЕ** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и может использоваться только в прологе, который расширяется из объявления кадра [процесса](proc.md) в [. ](dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. СЕТФРАМЕ** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Образец

### <a name="description"></a>Описание

В следующем примере показано использование указателя фрейма:

### <a name="code"></a>Код

```asm
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE
_text SEGMENT
frmex2 PROC FRAME
   push rbp
.pushreg rbp
   sub rsp, 010h
.allocstack 010h
   mov rbp, rsp
.setframe rbp, 0
.endprolog
   ; modify the stack pointer outside of the prologue (similar to alloca)
   sub rsp, 060h

   ; we can unwind from the following AV because of the frame pointer
   mov rax, 0
   mov rax, [rax] ; AV!

   add rsp, 060h
   add rsp, 010h
   pop rbp
   ret
frmex2 ENDP
_text ENDS
END
```

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
