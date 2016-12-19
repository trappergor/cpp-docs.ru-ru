---
title: "Ошибка профильной оптимизации PG0165 | Microsoft Docs"
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
  - "PG0165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PG0165"
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка профильной оптимизации PG0165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтение "Filename.pgd": "версия PGD не поддерживается \(неподходящая версия\)  
  
 Файлы PGD соответствуют определенному набору инструментов компилятора.  Эта ошибка возникает при использовании другого компилятора одного служит для *Filename*.pgd.  Эта ошибка указывает, что этот набор инструментов компилятора не могут использоваться данные из *Filename*.pgd, чтобы оптимизировать текущей программы.  
  
 Чтобы разрешить эту проблему, regenerate *Filename*.pgd с помощью текущего набора инструментов компилятора.