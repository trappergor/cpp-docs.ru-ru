---
title: "Ошибка вычислителя выражений CXX0016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0016"
  - "CXX0016"
ms.assetid: af94a2ae-e835-4da6-8d2f-5c879f72eda2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка вычислителя выражений CXX0016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком большая константа  
  
 Вычислитель выражений C не принимает целочисленные константы без знака, значение которых превышает 4 294 967 295 \(0FFFFFFFF в шестнадцатеричной записи\), или константы с плавающей запятой, порядок которых превышает приблизительно 1,8E\+308.  
  
 Эта ошибка идентична ошибке CAN0016.