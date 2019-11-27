---
title: .SETFRAME
ms.date: 08/30/2018
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: a21dda496d32abcfeb4692d0228afdbcfd4e5ebb
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397933"
---
# <a name="setframe"></a>.SETFRAME

Заполняет поле регистра кадра и смещение в данных очистки, используя указанный регистр (*reg*) и смещение (*смещение*). Смещение должно быть кратным 16 и меньше или равно 240. Эта директива также создает `UWOP_SET_FPREG` запись кода очистки для указанного регистра, используя текущее смещение пролога.

## <a name="syntax"></a>Синтаксис

> **. СЕТФРАМЕ** *reg*, *смещение*

## <a name="remarks"></a>Примечания

**. СЕТФРАМЕ** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и может использоваться только в прологе, который расширяется из объявления кадра [процесса](../../assembler/masm/proc.md) в [. ](../../assembler/masm/dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. СЕТФРАМЕ** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Пример

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

[Справочник по директивам](directives-reference.md)
