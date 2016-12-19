---
title: "Ошибка во время выполнения C R6025 | Microsoft Docs"
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
  - "R6025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6025"
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка во время выполнения C R6025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

вызов чистой виртуальной функции  
  
 Для обработки вызова чистой виртуальной функции не был создан экземпляр объекта.  
  
 Если сообщение об этой ошибке выводится приложением, обратитесь в службу технической поддержки данного приложения.  
  
 Причиной данной ошибки служит вызов виртуальной функции в абстрактном базовом классе посредством указателя, созданного путем приведения к типу производного класса, но который в действительности является указателем на базовый класс.  Это может произойти при приведении от типа **void\*** к указателю на класс, если **void\*** был создан при создании базового класса.  
  
 Дополнительные сведения см. на веб\-узле [Поддержка Майкрософт](http://go.microsoft.com/fwlink/?LinkId=75220).