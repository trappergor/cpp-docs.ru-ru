---
title: Необработанные псевдооперации
ms.date: 11/04/2016
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
ms.openlocfilehash: 04dfe4d59c05dfcf22d0e64063fbc4953cbcb2f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538038"
---
# <a name="raw-pseudo-operations"></a>Необработанные псевдооперации

В этом разделе перечислены псевдооперации.

## <a name="remarks"></a>Примечания

|Псевдо-операции|Описание|
|----------------------|-----------------|
|PROC ФРЕЙМА [: обработчика ошибок]|Причины MASM для создания функции запись в .pdata таблицы и очистки информацию в XDATA для функции структурной обработки исключений очистки поведение.  При наличии обработчика ошибок Данная процедура вводится в xdata как обработчик конкретного языка.<br /><br /> При использовании атрибута КАДРА, его следует указать. Директива ENDPROLOG.  Если функция является конечной (как определено в [типы функций](../build/function-types.md)) атрибута FRAME необязателен, как и остальная часть этих псевдо операций.|
|. PUSHREG reg|Создает UWOP_PUSH_NONVOL запись для указанного номера регистра с использованием текущего смещения в прологе.<br /><br /> Это свойство следует использовать только с защищенных целочисленные регистры.  Push-уведомлений переменные регистры, использовать. ALLOCSTACK 8 вместо|
|. Смещение SETFRAME reg|Заливки в окне регистрации поля и смещение в информацию очистки с помощью указанного регистра и смещения. Смещение должно быть кратным 16 и меньше или равно 240. Эта директива также создает в коде завершения UWOP_SET_FPREG очистки запись для указанного регистра, с помощью текущего смещения пролога.|
|. Размер ALLOCSTACK|Создает UWOP_ALLOC_SMALL или UWOP_ALLOC_LARGE заданного размера для текущего смещения в прологе.<br /><br /> Размер операнд должен быть кратен 8.|
|. Смещение SAVEREG reg|Создает UWOP_SAVE_NONVOL или UWOP_SAVE_NONVOL_FAR запись для указанного регистра и смещение, с помощью текущего смещения пролога. MASM выберет наиболее эффективную кодировку.<br /><br /> Смещение должно быть положительным и кратен 8.  Смещение выполняется относительно базового процедуры кадра, который обычно находится в RSP, или указатель немасштабированным кадра.|
|. Смещение SAVEXMM128 reg|Создает UWOP_SAVE_XMM128 или UWOP_SAVE_XMM128_FAR запись для указанного регистра XMM и смещение, с помощью текущего смещения пролога. MASM выберет наиболее эффективную кодировку.<br /><br /> Смещение должно быть положительным и кратен 16.  Смещение выполняется относительно базового процедуры кадра, который обычно находится в RSP, или указатель немасштабированным кадра.|
|. PUSHFRAME [код]|Создает запись UWOP_PUSH_MACHFRAME очистки кода. Если указан дополнительный код, запись присваивается модификатор 1. В противном случае модификатор равно 0.|
|.ENDPROLOG|Сигнализирует об окончании объявлений пролога.  Должен существовать в первые 255 байт функции.|

Ниже приведен пример пролога функции использование большинства кодов операций.

```
sample PROC FRAME
   db      048h; emit a REX prefix, to enable hot-patching
push rbp
.pushreg rbp
sub rsp, 040h
.allocstack 040h
lea rbp, [rsp+020h]
.setframe rbp, 020h
movdqa [rbp], xmm7
.savexmm128 xmm7, 020h;the offset is from the base of the frame
;not the scaled offset of the frame
mov [rbp+018h], rsi
.savereg rsi, 038h
mov [rsp+010h], rdi
.savereg rdi, 010h; you can still use RSP as the base of the frame
; or any other register you choose
.endprolog

; you can modify the stack pointer outside of the prologue (similar to alloca)
; because we have a frame pointer.
; if we didn’t have a frame pointer, this would be illegal
; if we didn’t make this modification,
; there would be no need for a frame pointer

sub rsp, 060h

; we can unwind from the following AV because of the frame pointer

mov rax, 0
mov rax, [rax] ; AV!

; restore the registers that weren’t saved with a push
; this isn’t part of the official epilog, as described in section 2.5

movdqa xmm7, [rbp]
mov rsi, [rbp+018h]
mov rdi, [rbp-010h]

; Here’s the official epilog

lea rsp, [rbp-020h]
pop rbp
ret
sample ENDP
```

## <a name="see-also"></a>См. также

[Вспомогательные процедуры раскрутки для MASM](../build/unwind-helpers-for-masm.md)