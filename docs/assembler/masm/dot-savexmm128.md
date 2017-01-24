---
title: ".SAVEXMM128 | Microsoft Docs"
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
  - ".SAVEXMM128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEXMM128 directive"
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEXMM128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает то a `UWOP_SAVE_XMM128` или a  `UWOP_SAVE_XMM128_FAR` запись кода раскрутки для указанного регистра XMM и смещения, используя текущее смещение в прологе.  Компилятор MASM выберет наиболее подходящий способ кодировки.  
  
## Синтаксис  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## Заметки  
 .SAVEXMM128 позволяет пользователям ml64.exe, чтобы указать, как функция с кадром очистки и допустимо только внутри пролога, который распространяется от [PROC](../../assembler/masm/proc.md) объявление КАДРА к  [.ENDPROLOG](../Topic/.ENDPROLOG.md) директива.  Эти правила не создают код; они лишь создают `.xdata` и  `.pdata`.  .SAVEXMM128 должен предшествовать инструкциям, которые фактически реализуют действия, размотанным.  Рекомендуется создавать программу\-оболочку и рекомендации очистки и код предназначен для раскрутки в макросе для предоставления соглашения.  
  
 `offset` должна быть кратной 16.  
  
 Дополнительные сведения см. в разделе [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)