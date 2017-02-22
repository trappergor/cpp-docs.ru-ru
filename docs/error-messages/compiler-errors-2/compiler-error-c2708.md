---
title: "Ошибка компилятора C2708 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2708"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2708"
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2708
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : длина фактических параметров в байтах отличается от предыдущего вызова или ссылки  
  
 Функции [\_\_stdcall](../../cpp/stdcall.md) должен предшествовать прототип.  В противном случае компилятор интерпретирует первый вызов функции как прототип, и эта ошибка возникает, когда компилятор сталкивается с несоответствующим вызовом.  
  
 Для исправления ошибки добавьте прототип функции.