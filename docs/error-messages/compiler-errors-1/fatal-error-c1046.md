---
title: "Неустранимая ошибка C1046 | Microsoft Docs"
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
  - "C1046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1046"
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора: недопустимая степень вложения структур  
  
 Превышен максимально допустимый уровень вложенности структур, объединений или классов \(15 уровней\).  Измените определение или уменьшите уровень вложенности.  Разбейте структуру, объединение или класс на несколько частей. Для этого с помощью ключевого слова `typedef` определите одну или несколько вложенных структур.