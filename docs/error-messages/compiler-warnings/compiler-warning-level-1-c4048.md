---
title: "Предупреждение компилятора (уровень 1) C4048 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4048"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4048"
ms.assetid: 8429f513-4732-40f1-8e56-4c224e723bcb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4048
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

разные индексы массива: "идентификатор1" и "идентификатор2"  
  
 В выражении используются указатели на массивы разного размера.  Указатели используются без преобразования.  
  
 Чтобы устранить это предупреждение, выполните явное приведение массивов к одинаковым или эквивалентным типам.