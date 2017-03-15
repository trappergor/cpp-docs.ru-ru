---
title: "Неустранимая ошибка C1603 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1603"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1603"
ms.assetid: e5a06925-f916-4637-8240-6d2d280e6124
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1603
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

конечный адрес ветвления ассемблерной вставки выходит за пределы на 'number' байт  
  
 Рассчитанное расстояние между инструкцией JCXZ или JECXZ и указанной целевой меткой больше 128 байт.  Измените код, чтобы метка располагалась ближе к инструкции.