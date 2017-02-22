---
title: "Математическая ошибка M6203 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6203"
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Математическая ошибка M6203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

функция: ошибка \_OVERFLOW  
  
 Результат, выданный функцией, слишком велик для представления.  
  
 Эта ошибка вызывает функцию `_matherr` с именем функции, ее аргументами и типом ошибок.  Можно переписать функцию `_matherr`, чтобы настроить обработку определенных математических ошибок с плавающей запятой времени выполнения.