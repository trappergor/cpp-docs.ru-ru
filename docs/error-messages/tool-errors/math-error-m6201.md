---
title: "Математическая ошибка M6201 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6201"
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Математическая ошибка M6201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": ошибка \_DOMAIN  
  
 Аргумент для данной функции находится вне домена допустимых входных значений для этой функции.  
  
## Пример  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 Эта ошибка вызывает функцию `_matherr` с именем функции, ее аргументами и типом ошибок.  Можно переписать функцию `_matherr`, чтобы настроить обработку определенных математических ошибок с плавающей запятой времени выполнения.