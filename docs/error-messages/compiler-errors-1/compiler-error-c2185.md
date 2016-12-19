---
title: "Ошибка компилятора C2185 | Microsoft Docs"
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
  - "C2185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2185"
ms.assetid: 74bc9f64-7b4c-4735-ba13-67c43f8c47db
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": недопустимое базовое выделение памяти  
  
 Переменная регистра или автоматически создаваемая \(локальная\) переменная объявляется с использованием ключевого слова `__based`.  Ключевое слово `__based` можно использовать только для объявления глобальных переменных.