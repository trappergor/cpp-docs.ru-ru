---
title: "VERSION (C/C++) | Microsoft Docs"
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
  - "VERSION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VERSION - оператор DEF-файла"
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VERSION (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает программе LINK на необходимость указания номера в заголовке файла EXE или DLL.  
  
```  
VERSION major[.minor]  
```  
  
## Заметки  
 Аргументы *major* и *minor* — это десятичные числа в диапазоне от 0 до 65 535.  По умолчанию используется версия 0.0.  
  
 Эквивалентный способ задания номера версии — это использование параметра [Сведения о версии](../Topic/-VERSION%20\(Version%20Information\).md) \(\/VERSION\).  
  
## См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)