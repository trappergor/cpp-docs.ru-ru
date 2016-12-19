---
title: "Разряды | Microsoft Docs"
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
  - "разряды"
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Разряды
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Структура битовых полей ограничивается 64 битами и может быть следующих типов: signed int, unsigned int, int64 или unsigned int64.  Битовые поля, которые пересекают границу типов, пропустят биты, чтобы выровнять разряды до уровня следующего типа.  Например, разряды целого числа \(integer\) не могут пересечь 32\-разрядную границу.  
  
## См. также  
 [Типы и хранилище](../build/types-and-storage.md)