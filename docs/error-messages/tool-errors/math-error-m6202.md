---
title: "Математическая ошибка M6202 | Microsoft Docs"
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
  - "M6202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6202"
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Математическая ошибка M6202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": ошибка \_SING  
  
 Аргумент для данной функции является значением сингулярности для этой функции.  Функция не определена для данного аргумента.  
  
 Эта ошибка вызывает функцию `_matherr` с именем функции, ее аргументами и типом ошибок.  Можно переписать функцию `_matherr`, чтобы настроить обработку определенных математических ошибок с плавающей запятой времени выполнения.