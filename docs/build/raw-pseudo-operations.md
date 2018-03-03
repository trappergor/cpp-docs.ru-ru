---
title: "Необработанные псевдооперации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52ce7fb4455f87001bcfe87e1368ed0c09cda6b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="raw-pseudo-operations"></a>Необработанные псевдооперации
В этом разделе перечислены псевдооперации.  
  
## <a name="remarks"></a>Примечания  
  
|Операция псевдо|Описание:|  
|----------------------|-----------------|  
|КАДР PROC [: обработчика ошибок]|Причины MASM для создания функции запись в .pdata таблицы и очистки информацию в XDATA для функции структурной обработки исключений очистки поведение.  При наличии обработчика ошибок Данная процедура вводится в xdata как обработчик конкретного языка.<br /><br /> При использовании атрибута КАДР, он должен следовать. Директива ENDPROLOG.  Если функция является конечной (как определено в [типы функций](../build/function-types.md)) атрибут FRAME необязателен, как и в оставшейся части этих псевдо операций.|  
|. PUSHREG reg|Приводит к возникновению ошибки завершения UWOP_PUSH_NONVOL запись для указанного номера регистра с помощью текущего смещения в прологе.<br /><br /> Это должно использоваться только с защищенным целочисленным регистрам.  Отправок переменные регистры, использовать. ALLOCSTACK 8 вместо|  
|. Смещение SETFRAME reg|Заливки в кадре зарегистрировать поля и смещение в информации для раскрутки с помощью указанного регистра и смещения. Смещение должно быть кратным 16 и меньше или равно 240. Эта директива также приводит к возникновению ошибки в коде завершения UWOP_SET_FPREG очистки запись для указанного регистра, используя текущее смещение в прологе.|  
|. Размер ALLOCSTACK|Создает UWOP_ALLOC_SMALL или UWOP_ALLOC_LARGE с указанным размером для текущее смещение в прологе.<br /><br /> Размер операнд должен быть кратен 8.|  
|. Смещение SAVEREG reg|Создает UWOP_SAVE_NONVOL или UWOP_SAVE_NONVOL_FAR запись для указанного регистра и смещения, используя текущее смещение в прологе. MASM выберет наиболее эффективную кодировку.<br /><br /> Смещение должно быть положительным и кратным 8.  Смещение определяется относительно базовый процедуры кадра, который является обычно RSP, или указатель фрейма зависимым.|  
|. Смещение SAVEXMM128 reg|Приводит к возникновению ошибки UWOP_SAVE_XMM128 или UWOP_SAVE_XMM128_FAR запись для указанного регистра XMM и смещения, используя текущее смещение в прологе. MASM выберет наиболее эффективную кодировку.<br /><br /> Смещение должно быть положительным и кратным 16.  Смещение определяется относительно базовый процедуры кадра, который является обычно RSP, или указатель фрейма зависимым.|  
|. PUSHFRAME [код]|Создает запись UWOP_PUSH_MACHFRAME очистки кода. Если указан дополнительный код, операция очистки кода получает модификатор 1. В противном случае модификатор — 0.|  
|.ENDPROLOG|Сигнализирует о завершении объявлений в прологе.  Должен существовать в первые 255 байт функции.|  
  
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