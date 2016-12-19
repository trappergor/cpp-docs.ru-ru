---
title: "Вычисление необходимых значений | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "вспомогательные функции, вычисление необходимых значений"
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Вычисление необходимых значений
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Необходимо вычислить два критичных участка данных с помощью отложенной вспомогательной программы.  Существуют две встроенные функции в Delayhlp.cpp, которые служат для вычисления данных.  
  
-   Первая функция выполняет вычисление индекса текущего импортируемого элемента в три различных таблицы \(адресную таблицу импорта \(IAT\), связанную адресную таблицу импорта \(BIAT\) и несвязанную адресную таблицу импорта \(UIAT\)\).  
  
-   Вторая функция выполняет подсчет количества импортируемых элементов в действительной таблице IAT.  
  
```  
// utility function for calculating the index of the current import  
// for all the tables (INT, BIAT, UIAT, and IAT).  
__inline unsigned  
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {  
    return pitdCur - pitdBase;  
    }  
  
// utility function for calculating the count of imports given the base  
// of the IAT. NB: this only works on a valid IAT!  
__inline unsigned  
CountOfImports(PCImgThunkData pitdBase) {  
    unsigned        cRet = 0;  
    PCImgThunkData  pitd = pitdBase;  
    while (pitd->u1.Function) {  
        pitd++;  
        cRet++;  
        }  
    return cRet;  
    }  
```  
  
## См. также  
 [Understanding the Helper Function](http://msdn.microsoft.com/ru-ru/6279c12c-d908-4967-b0b3-cabfc3e91d3d)