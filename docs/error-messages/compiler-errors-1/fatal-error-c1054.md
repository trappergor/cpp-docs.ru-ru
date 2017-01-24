---
title: "Неустранимая ошибка C1054 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1054"
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора : инициализаторы вложены слишком глубоко  
  
 В коде превышен предел уровней вложенности инициализаторов \(10–15 уровней в зависимости от инициализируемого набора типов\).  
  
### Возможные способы устранения данной ошибки  
  
1.  Упростите инициализируемые типы данных, чтобы уменьшить уровень вложенности.  
  
2.  Инициализируйте переменные в отдельных операторах после объявления.