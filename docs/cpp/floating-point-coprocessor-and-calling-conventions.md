---
title: "Сопроцессор с плавающей запятой и соглашения о вызовах | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сопроцессор с плавающей запятой"
  - "числа с плавающей запятой"
  - "числа с плавающей запятой, сопроцессор"
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Сопроцессор с плавающей запятой и соглашения о вызовах
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если при написании подпрограмм сборки для сопроцессора вычислений с плавающей запятой значение **float** или **double** \(которое функция должна возвращать в ST\(0\)\) возвращаться не будет, следует сохранить контрольный регистр процессора с плавающей запятой и очистить стек сопроцессора.  
  
## См. также  
 [Соглашения о вызовах](../Topic/Calling%20Conventions.md)