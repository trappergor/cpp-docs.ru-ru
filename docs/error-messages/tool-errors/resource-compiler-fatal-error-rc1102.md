---
title: "Неустранимая ошибка компилятора ресурсов RC1102 | Microsoft Docs"
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
  - "RC1102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1102"
ms.assetid: bd2091f8-ef5e-4151-a8d6-98043e9422b6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка компилятора ресурсов RC1102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

внутренняя ошибка: Недопустимо большое число аргументов "RCPP"  
  
 Слишком много аргументов было передано препроцессору компилятора ресурсов.  Уменьшите количество символов, определенных при помощи параметра Define Symbols \(\/d\), определив их в исходном коде.  Эта ошибка также может быть вызвана указанием слишком большого количества включенных путей поиска файлов при помощи параметра Include Search Path \(\/i\).