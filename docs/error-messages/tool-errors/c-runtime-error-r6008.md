---
title: "Ошибка во время выполнения R6008 C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6008"
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка во время выполнения C R6008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недостаточно пространства для аргументов  
  
 Памяти достаточно для загрузки программы, но недостаточно для создания массива **argv**.  
  
### Возможные способы устранения данной ошибки  
  
1.  Увеличьте объем памяти, доступной для программы.  
  
2.  Уменьшите число и размер аргументов командной строки.  
  
3.  Уменьшите размер среды, удалив неиспользуемые переменные.