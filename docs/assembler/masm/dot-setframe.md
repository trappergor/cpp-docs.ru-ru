---
title: ".SETFRAME | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".SETFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SETFRAME directive"
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SETFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Заполняет поле и смещение регистра кадра в данных раскрутки, используя указанный регистр \(`reg`и смещение \(\)`offset`\).  Смещение должно быть кратным 16 и меньшим или равным 240.  Эта директива также создает a `UWOP_SET_FPREG` запись кода раскрутки для указанного регистра, используя текущее смещение в прологе.  
  
## Синтаксис  
  
```  
.SETFRAME reg, offset  
```  
  
## Заметки  
 .SETFRAME Позволяет пользователям ml64.exe, чтобы указать, как функция с кадром очистки и допустимо только внутри пролога, который распространяется от [PROC](../../assembler/masm/proc.md) объявление КАДРА к  [.ENDPROLOG](../Topic/.ENDPROLOG.md) директива.  Эти правила не создают код; они лишь создают `.xdata` и  `.pdata`.  .SETFRAME Должен предшествовать инструкциям, которые фактически реализуют действия, размотанным.  Рекомендуется создавать программу\-оболочку и рекомендации очистки и код предназначен для раскрутки в макросе для предоставления соглашения.  
  
 Дополнительные сведения см. в разделе [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Пример  
  
### Описание  
 В следующем образце показано, как использовать указатель кадра.  
  
### Код  
  
```  
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
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)