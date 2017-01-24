---
title: "Предупреждение компилятора (уровень&#160;1) C4041 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4041"
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;1) C4041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора: завершение вывода браузера  
  
 Информация для браузера превысила установленный для компилятора предел.  
  
 Это предупреждение может быть вызвано компиляцией с параметром [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) \(информация для браузера включает локальные переменные\).  
  
### Возможные способы устранения этой ошибки  
  
1.  Выполните компиляцию с параметром \/Fr \(информация для браузера без локальных переменных\).  
  
2.  Отключите вывод информации для браузера \(выполните компиляцию без параметра \/FR или \/Fr\).