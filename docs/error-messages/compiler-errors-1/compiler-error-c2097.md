---
title: "Ошибка компилятора C2097 | Microsoft Docs"
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
  - "C2097"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2097"
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2097
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимая инициализация  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Инициализация переменной с использованием неконстантного значения.  
  
2.  Инициализация короткого адреса с использованием длинной формы адреса.  
  
3.  Иницализация локальной структуры, объединения или массива с использованием неконстантного выражения \(при компиляции с параметром **\/Za**\).  
  
4.  Инициализация с использованием выражения, содержащего оператор\-запятую.  
  
5.  Инициализация с использованием выражения, не являющегося константным или символьным.