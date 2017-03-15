---
title: "Предупреждение компилятора (уровень 4) C4931 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4931"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4931"
ms.assetid: cfbf08c7-94e4-4a91-a691-479d1dbe527a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4931
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

предполагается, что при построении библиотека типов была рассчитана на "число"\-разрядные указатели  
  
 Сведения не были заданы явно с помощью атрибута **ptrsize** директивы [\#import](../Topic/%23import%20Directive%20\(C++\).md); компилятор предполагает, что размер указателей в библиотеке типов составляет ***число***.  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Отключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).