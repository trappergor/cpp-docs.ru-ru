---
title: "Предупреждение компилятора (уровень 1) C4506 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4506"
ms.assetid: aa682869-65d1-4dad-ba32-198f10b44f91
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нет определения для встроенной функции "функция"  
  
 Данная функция была объявлена и помечена как подлежащая встраиванию, но не была определена.  
  
 Встраивание не было произведено компилятором.  
  
 Убедитесь, что внешние функции, подлежащие встраиванию, объявляются с помощью ключевого слова `extern`.