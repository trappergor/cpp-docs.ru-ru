---
title: "Предупреждение компилятора (уровень 3) C4013 | Microsoft Docs"
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
  - "C4013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4013"
ms.assetid: 9f9afc71-6e78-463d-9d66-3012d6a3cd5d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" не определена; предполагается функция extern, возвращающая int  
  
 Компилятор обнаружил вызов функции, которая не была определена.  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Неверное написание имени функции  
  
2.  Не созданы прототипы внешних функций с помощью `extern`