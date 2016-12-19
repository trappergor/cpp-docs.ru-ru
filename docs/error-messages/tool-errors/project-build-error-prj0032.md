---
title: "Ошибка построения проекта PRJ0032 | Microsoft Docs"
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
  - "PRJ0032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0032"
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка построения проекта PRJ0032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Свойство 'Outputs' для этапа пользовательского построения уровня проекта содержит 'macro', который превышает 'macro\_expansion'.  
  
 Этап пользовательского построения проекта, возможно, дает некорректный вывод из\-за проблемы выхода макроса за границы области.  Эта ошибка также может означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути файла.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути.  Анализируемый путь является абсолютным путем относительно каталога проекта.