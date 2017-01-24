---
title: "Предупреждение компилятора (уровень 1) C4049 | Microsoft Docs"
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
  - "C4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4049"
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора: завершение вывода номеров строк  
  
 Файл содержит более 16777215 \(2<sup>24</sup>\-1\) исходных строк.  Нумерация строк компилятора ограничена числом 16777215.  
  
 Сведения о кодах после строки 16777215  
  
-   Изображение не будет содержать отладочную информацию для номеров строк.  
  
-   При некоторых диагностических операциях могут определяться неверные номера строк.  
  
-   Списки ASM \(\/FAs\) могут содержать неверные номера строк.