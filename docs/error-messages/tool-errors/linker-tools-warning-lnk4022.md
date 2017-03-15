---
title: "Предупреждение средств компоновщика LNK4022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4022"
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение средств компоновщика LNK4022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается найти уникальное соответствие для символа "символ"  
  
 Программой LINK или LIB обнаружено несколько соответствий для указанного не являющегося внутренним символа, что привело к возникновению неоднозначности.  Выходной файл \(EXE, DLL, EXP или LIB\) не создается.  Вслед за этим предупреждением отображается предупреждение [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) для каждого повторяющегося символа, после чего возникает неустранимая ошибка [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Чтобы устранить это предупреждение, задайте символ с использованием его внутренней формы.  Чтобы просмотреть внутренние имена для объекта, запустите программу [DUMPBIN](../../build/reference/dumpbin-options.md).