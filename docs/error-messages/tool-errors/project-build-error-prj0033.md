---
title: "Ошибка построения проекта PRJ0033 | Microsoft Docs"
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
  - "PRJ0033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0033"
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка построения проекта PRJ0033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Свойство "Дополнительные зависимости" этапа настраиваемого построения для файла "файл" содержало "макрос", что вычисляется как "расширение макроса".  
  
 На этапе настраиваемого построения файла возникла ошибка дополнительных зависимостей, возможно, связанная с ошибками при вычислении макроса.  Эта ошибка также может означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути файла.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути.  Анализируемый путь является абсолютным путем относительно каталога проекта.