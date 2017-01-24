---
title: "Объявления и определения в C | Microsoft Docs"
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
  - "C"
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Объявления и определения в C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объявление устанавливает связь между указанной переменной, функцией или типом и их атрибутами.  В разделе [Обзор объявлений](../Topic/Overview%20of%20Declarations.md) приводится синтаксис ANSI для нетерминальных символов `declaration`.  В объявлении также определяется, где и когда возможен доступ к идентификатору \("компоновка" идентификатора\).  Дополнительные сведения о компоновке см. в разделе [Время существования, область, видимость и компоновка](../Topic/Lifetime,%20Scope,%20Visibility,%20and%20Linkage.md).  
  
 Определение переменной устанавливает те же связи, что и объявление, но также приводит к выделению памяти для переменной.  
  
 Например, функции `main`, `find` и `count` и переменные `var` и `val` определяются в одном исходном файле в следующем порядке:  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 Переменные `var` и `val` могут использоваться в функциях `find` и `count`; никакие дополнительные объявления не требуются.  Однако в функции `main` эти имена не видны \(доступ к ним невозможен\).  
  
## См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)