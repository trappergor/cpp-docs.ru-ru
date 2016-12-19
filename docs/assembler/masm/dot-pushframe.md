---
title: ".PUSHFRAME | Microsoft Docs"
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
  - ".PUSHFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".PUSHFRAME directive"
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .PUSHFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает a `UWOP_PUSH_MACHFRAME` завершение записи.  Если необязательный `code` определяет запись кода раскрутки дает модификатор 1.  В противном случае используется модификатор 0.  
  
## Синтаксис  
  
```  
.PUSHFRAME [code]  
```  
  
## Заметки  
 .PUSHFRAME Позволяет пользователям ml64.exe, чтобы указать, как функция с кадром очистки и допускается только в пределах пролога, который распространяется от [PROC](../../assembler/masm/proc.md) объявление КАДРА к  [.ENDPROLOG](../Topic/.ENDPROLOG.md) директива.  Эти правила не создают код; они лишь создают `.xdata` и  `.pdata`.  .PUSHFRAME Должен предшествовать инструкциям, которые фактически реализуют действия, размотанным.  Рекомендуется создавать программу\-оболочку и рекомендации очистки и код предназначен для раскрутки в макросе для предоставления соглашения.  
  
 Дополнительные сведения см. в разделе [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)