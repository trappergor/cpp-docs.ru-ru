---
title: "Определение правила | Microsoft Docs"
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
helpviewer_keywords: 
  - "определение правил зависимости"
  - "программа NMAKE, правила зависимости"
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Определение правила
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Параметр *fromext* представляет расширение зависимого файла, а *toext* — расширение целевого файла.  
  
```  
.fromext.toext:  
   commands  
```  
  
## Заметки  
 В расширениях регистр знаков не учитывается.  Для представления параметров *fromext* и *toext* можно использовать макросы, которые развертываются во время предварительной обработки.  В начале строки перед параметром *fromext* должна стоять точка \("."\).  Перед двоеточием \(":"\) следует 0 или более пробелов или знаков табуляции.  За ним могут следовать только пробелы или знаки табуляции, точка с запятой \(";"\) для указания команды, знак решетки \("\#"\) для указания комментария или знак начала новой строки.  Другие пробелы не допускаются.  Команды указываются так же, как в блоках описания.  
  
## Дополнительные сведения  
 [Пути поиска в правилах](../build/search-paths-in-rules.md)  
  
## См. также  
 [Правила вывода](../build/inference-rules.md)