---
title: . SETFRAME | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SETFRAME
dev_langs:
- C++
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 956a49e40c38310819d66e89fa6bf4492443a29c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691293"
---
# <a name="setframe"></a>.SETFRAME

Заливки в окне регистрации поля и смещение в информацию очистки с помощью указанного регистра (`reg`) и смещения (`offset`). Смещение должно быть кратным 16 и меньше или равно 240. Эта директива также создает `UWOP_SET_FPREG` очистки записи кода для указанного зарегистрировать с помощью текущего смещения пролога.

## <a name="syntax"></a>Синтаксис

> . Смещение SETFRAME reg

## <a name="remarks"></a>Примечания

. SETFRAME позволяет ml64.exe пользователю указать, каким образом функция кадра освобождает и разрешен только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директива. Эти директивы не создают код; они создают только `.xdata` и `.pdata`. . SETFRAME должно предшествовать инструкции, которые на деле реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе для обеспечения соглашения.

Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Пример

### <a name="description"></a>Описание

Следующий пример показано, как использовать указатель фрейма:

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

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>