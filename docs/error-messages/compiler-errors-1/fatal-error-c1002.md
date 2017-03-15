---
title: "Неустранимая ошибка C1002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1002"
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не хватает размера кучи на 2\-ом проходе компилятора  
  
 Компилятор вышел за границы пространства динамической памяти во время второго прогона, возможно, из\-за того, что в программе слишком много символов или комплексных выражений.  
  
### Возможные способы устранения данной ошибки  
  
1.  Разделите исходных файл на несколько меньших по размеру файлов.  
  
2.  Разделите выражения на более маленькие подвыражения.  
  
3.  Удалите другие программы или драйвера, использующие память.