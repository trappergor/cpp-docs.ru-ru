---
title: "Ошибка компилятора C3888 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3888"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3888"
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Ошибка компилятора C3888
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя": выражение константы, связанное с этими данными\-членом литерала, не поддерживается в C\+\+\/CLI  
  
 Член данных *имя*, объявленный с помощью ключевого слова [literal](../../windows/literal-cpp-component-extensions.md), инициализирован со значением, не поддерживаемым компилятором. Компилятор поддерживает только целочисленные константы, перечисления и строковые типы. Возможной причиной ошибки **C3888** может быть то, что член данных инициализирован с помощью байтового массива.  
  
### Исправление ошибки  
  
1.  Проверьте, имеет ли объявленный член данных литерала поддерживаемый тип.  
  
## См. также  
 [literal](../../windows/literal-cpp-component-extensions.md)