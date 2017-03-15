---
title: "Ошибка построения проекта PRJ0031 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0031"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0031"
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка построения проекта PRJ0031
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Свойство 'Outputs' пользовательского построения применяется к файлу 'file', содержащему 'macro', который принимает значение большее, чем 'macro\_expansion'.  
  
 Этап настраиваемого построения в файле, возможно, выдает некорректный вывод из\-за макроса, вызывающего проблемы.  Эта ошибка также может означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути файла.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути.  Анализируемый путь является абсолютным путем относительно каталога проекта.