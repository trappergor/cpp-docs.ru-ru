---
title: "Предупреждение компилятора (уровень 4) C4611 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4611"
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

взаимодействие между "функцией" и деструктором объектов C\+\+ не будет переносимым  
  
 В некоторых платформах функции, включающие **catch**, возможно, не поддерживают семантику уничтожения объектов в C\+\+ при выходе за область действия.  
  
 Чтобы избежать непредсказуемого поведения, избегайте использования **catch** в функциях, имеющих конструкторы и деструкторы.  
  
 Это предупреждение показывается только один раз; см. раздел [pragma warning](../../preprocessor/warning.md).