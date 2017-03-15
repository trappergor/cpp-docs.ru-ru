---
title: "Naked (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "код эпилога"
  - "naked - ключевое слово [C]"
  - "naked - ключевое слово [C], storage-class - атрибут"
  - "код пролога"
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Naked (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Атрибут класса хранения naked является расширением языка C для систем Microsoft.  Код функций, объявленных с этим атрибутом, создается компилятором без кода пролога и эпилога.  Благодаря этому вы можете вставить в качестве пролога и эпилога свой собственный код на языке ассемблера.  Функции с атрибутом naked полезны для написания драйверов виртуальных устройств.  
  
 Дополнительные сведения см. в разделе [Функции с атрибутом naked](../c-language/naked-functions.md).  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)