---
title: "Необработанные псевдооперации | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Необработанные псевдооперации
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе перечислены псевдооперации.  
  
## Заметки  
  
|Псевдооперация|Описание|  
|--------------------|--------------|  
|PROC FRAME \[:ehandler\]|Приводит к тому, что компилятор MASM создает запись в таблице функции в PDATA и раскручивает информацию в XDATA для структурной обработки исключений функции при раскрутке.  При наличии обработчика ошибок данная процедура вводится в XDATA как языковой обработчик.<br /><br /> При использовании атрибута FRAME за ним обязательно должна следовать директива .ENDPROLOG.  Если функция является конечной \(в соответствии с разделом [Типы функций](../build/function-types.md)\), атрибут FRAME является необязательным, так же как и остатки этих псевдоопераций.|  
|.PUSHREG reg|Создает в коде завершения UWOP\_PUSH\_NONVOL запись для указанного номера регистра с помощью текущего смещения в прологе.<br /><br /> Следует применять эту операцию только к защищенным целочисленным регистрам.  Для передачи временных регистров следует использовать ALLOCSTACK 8.|  
|.SETFRAME reg, offset|Заполняет поле регистра для фреймов и указывает смещение в информации для раскрутки с помощью указанного регистра и смещения.  Смещение должно быть кратным 16 и меньшим или равным 240.  Данная директива также создает в коде завершения UWOP\_SET\_FPREG запись для указанного регистра с помощью текущего смещения в прологе.|  
|.ALLOCSTACK size|Создает код UWOP\_ALLOC\_SMALL или UWOP\_ALLOC\_LARGE с указанным размером текущего смещения в прологе.<br /><br /> Операнд size должен быть кратным 8.|  
|.SAVEREG reg, offset|Создает запись в коде завершения UWOP\_SAVE\_NONVOL или UWOP\_SAVE\_NONVOL\_FAR для указанного регистра и смещения, используя текущее смещение в прологе.  Компилятор MASM выберет наиболее подходящий способ кодировки.<br /><br /> Смещение должно иметь положительное значение и быть кратным 8.  Смещение указывается относительно кадра процедуры \(как правило, в RSP\) или указателя на кадр \(немасштабированный\).|  
|.SAVEXMM128 reg, offset|Создает запись в коде завершения UWOP\_SAVE\_XMM128 или UWOP\_SAVE\_XMM128\_FAR для указанного регистра XMM и смещения, используя текущее смещение в прологе.  Компилятор MASM выберет наиболее подходящий способ кодировки.<br /><br /> Смещение должно иметь положительное значение и быть кратным 16.  Смещение указывается относительно кадра процедуры \(как правило, в RSP\) или указателя на кадр \(немасштабированный\).|  
|.PUSHFRAME \[код\]|Создает запись в коде завершения UWOP\_PUSH\_MACHFRAME.  Если указан дополнительный код, к записи в код завершения добавляется модификатор 1.  В противном случае используется модификатор 0.|  
|.ENDPROLOG|Сообщает об окончании объявлений в прологе.  Находится в первых 255 байтах функции.|  
  
 Ниже представлен пример пролога функции, демонстрирующий допустимое использование большинства кодов операций.  
  
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
  
## См. также  
 [Завершение вспомогательных процедур для MASM](../build/unwind-helpers-for-masm.md)