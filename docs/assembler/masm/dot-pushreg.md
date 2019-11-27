---
title: .PUSHREG
ms.date: 08/30/2018
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: 2190bd05667de82dada34a63f11647c653f97247
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398026"
---
# <a name="pushreg"></a>.PUSHREG

Создает `UWOP_PUSH_NONVOL` запись кода очистки для указанного номера регистра, используя текущее смещение в прологе.

## <a name="syntax"></a>Синтаксис

> . ПУШРЕГ регистр

## <a name="remarks"></a>Примечания

**. ПУШРЕГ** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и может использоваться только в прологе, который расширяется из объявления кадра [процесса](../../assembler/masm/proc.md) в [. ](../../assembler/masm/dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. ПУШРЕГ** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Пример

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

[Справочник по директивам](directives-reference.md)
