---
title: "Предупреждение компилятора (уровень 1 and 4) C4223 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4223"
ms.assetid: 6fc44336-0250-4432-928b-fc5dbe7b7c1c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1 and 4) C4223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нестандартное расширение: преобразование массива, не являющегося lvalue, в указатель  
  
 В стандарте языка С нельзя выполнять преобразование массива, не являющегося lvalue, в указатель.  Это возможно при использовании стандартных расширений Microsoft \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).