---
title: "Неустранимая ошибка C1026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1026"
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка C1026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

переполнение стека синтаксического анализатора, слишком сложная программа  
  
 Переполнение стека компилятора, вызванное нехваткой памяти для синтаксического анализа программы.  
  
 Уменьшите уровень сложности выражений следующими способами:  
  
-   Уменьшите уровень вложения операторов `for` и `switch`.  Выделите операторы с наибольшим уровнем вложения в отдельные функции.  
  
-   Разбейте длинные выражения, в которых содержатся операторы\-запятые или вызовы функций.