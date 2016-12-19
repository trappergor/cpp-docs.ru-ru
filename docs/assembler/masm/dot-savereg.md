---
title: ".SAVEREG | Microsoft Docs"
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
  - ".SAVEREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEREG directive"
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEREG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает то a `UWOP_SAVE_NONVOL` или a  `UWOP_SAVE_NONVOL_FAR` запись кода раскрутки для указанного регистра \(`reg`и смещение \(\)`offset`\), используя текущее смещение в прологе.  Компилятор MASM выберет наиболее подходящий способ кодировки.  
  
## Синтаксис  
  
```  
.SAVEREG reg, offset  
```  
  
## Заметки  
 .SAVEREG Позволяет пользователям ml64.exe, чтобы указать, как функция с кадром очистки и допускается только в пределах пролога, который распространяется от [PROC](../../assembler/masm/proc.md) объявление КАДРА к  [.ENDPROLOG](../Topic/.ENDPROLOG.md) директива.  Эти правила не создают код; они лишь создают `.xdata` и  `.pdata`.  .SAVEREG Должен предшествовать инструкциям, которые фактически реализуют действия, размотанным.  Рекомендуется создавать программу\-оболочку и рекомендации очистки и код предназначен для раскрутки в макросе для предоставления соглашения.  
  
 Дополнительные сведения см. в разделе [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)