---
title: "Математическая ошибка M6110 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6110"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6110"
ms.assetid: aac9ae37-6a6d-46e9-85d4-dfe03f1c3e11
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Математическая ошибка M6110
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

переполнение стека  
  
 Выражения с плавающей запятой вызвало переполнение стека для чисел с плавающей запятой.  
  
 Исключения переполнения стека для чисел с плавающей запятой перехватываются максимум до седьмого уровня в дополнение к восьми уровням, обычно поддерживаемым сопроцессором 8087\/287\/387.  
  
 Программа завершается с кодом завершения 138.