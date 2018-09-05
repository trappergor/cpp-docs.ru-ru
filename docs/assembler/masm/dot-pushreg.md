---
title: . PUSHREG | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .PUSHREG
dev_langs:
- C++
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11d0e0456621dd77e1545e2e8a16662556bed944
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676043"
---
# <a name="pushreg"></a>.PUSHREG

Создает `UWOP_PUSH_NONVOL` очистки записи кода для указанного зарегистрировать номер, с помощью текущего смещения в прологе.

## <a name="syntax"></a>Синтаксис

> . Регистрация PUSHREG

## <a name="remarks"></a>Примечания

. PUSHREG позволяет ml64.exe пользователю указать, каким образом функция кадра освобождает и разрешен только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директива. Эти директивы не создают код; они создают только `.xdata` и `.pdata`. . PUSHREG должно предшествовать инструкции, которые на деле реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе для обеспечения соглашения.

Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Пример

### <a name="description"></a>Описание

Следующий пример показано, как для принудительной отправки долговременного tegisters.

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

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>