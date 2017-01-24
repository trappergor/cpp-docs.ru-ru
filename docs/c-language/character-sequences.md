---
title: "Последовательности знаков | Microsoft Docs"
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
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Последовательности знаков
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** Сопоставление последовательностей символов с исходным файлом  
  
 В операторах препроцессора используется тот же набор символов, что и в операторах исходного файла, однако escape\-последовательности не поддерживаются.  
  
 Таким образом, при определении пути к включаемому файлу необходимо указывать только одну обратную косую черту.  
  
```  
#include "path1\path2\myfile"  
```  
  
 Однако в самом исходном коде необходимо указывать две обратные косые черты подряд:  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## См. также  
 [Директивы предварительной обработки](../Topic/Preprocessing%20Directives.md)