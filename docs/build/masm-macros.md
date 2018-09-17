---
title: Макросы MASM | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb436acae117c78bfa5c752b905bd3f4f910e9da
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707854"
---
# <a name="masm-macros"></a>Макросы MASM

Чтобы упростить использование [Необработанные псевдооперации](../build/raw-pseudo-operations.md), существует набор макросов, определенных в файле ksamd64.inc, который может использоваться для создания типичных прологов и эпилогов.

## <a name="remarks"></a>Примечания

|Макрос|Описание|
|-----------|-----------------|
|alloc_stack(n)|Выделяет кадр стека (с помощью sub rsp, n) n байт и создает соответствующую информацию (.allocstack n) для раскрутки|
|reg save_reg, локализация|Сохраняет reg защищенный регистр стека на смещения loc RSP и помещает соответствующую информацию для раскрутки. (.savereg reg, loc)|
|push_reg reg|Помещает в стек reg защищенный регистр и создает соответствующую информацию для раскрутки. (.pushreg reg)|
|rex_push_reg reg|Сохраняет защищенный регистр в стеке с помощью извещающей 2 byte и выдает соответствующую информацию (.pushreg reg), это следует использовать при первой инструкции в функции, чтобы убедиться, что функция является исправлять "Горячий" Push-уведомления для раскрутки.|
|reg save_xmm128, локализация|Сохраняет reg энергонезависимого регистра XMM в стеке по RSP loc смещения и помещает соответствующую информацию (.savexmm128 reg, loc) для раскрутки|
|Смещение set_frame reg|Задает reg register кадра быть RSP + смещение (используя функцию mov или тавить) и выдает соответствующую информацию (.set_frame reg, смещение) для раскрутки|
|push_eflags|Помещает eflags с помощью команды pushfq и помещает соответствующую информацию (".alloc_stack 8") для раскрутки|

Ниже приведен пример пролога функции надлежащего использования макросов.

```asm
SkFrame struct
Fill    dq ?; fill to 8 mod 16
SavedRdi dq ?; saved register RDI
SavedRsi dq ?; saved register RSI
SkFrame ends

sampleFrame struct
Filldq?; fill to 8 mod 16
SavedRdidq?; Saved Register RDI
SavedRsi  dq?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
alloc_stack(sizeof sampleFrame)
save_reg rdi, sampleFrame.SavedRdi
save_reg rsi, sampleFrame.SavedRsi
.end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here’s the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="see-also"></a>См. также

[Вспомогательные процедуры раскрутки для MASM](../build/unwind-helpers-for-masm.md)