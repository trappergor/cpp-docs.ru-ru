---
title: "Функция abort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort - функция"
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Функция abort
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функция **abort**, также объявляемая в стандартном включаемом файле STDLIB.H, завершает программу C\+\+.  Различие между функциями **exit** и **abort** состоит в том, что при использовании функции **exit** происходит обработка завершения среды выполнения C\+\+ \(вызываются глобальные деструкторы объектов\), а при использовании функции **abort** программа завершается сразу.  Дополнительные сведения см. в разделе описания функции [abort](../c-runtime-library/reference/abort.md) *Справочника по библиотеке времени выполнения*.  
  
## См. также  
 [Завершение программы](../Topic/Program%20Termination.md)