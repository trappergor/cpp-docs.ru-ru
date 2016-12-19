---
title: "Неустранимая ошибка NMAKE U1070 | Microsoft Docs"
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
  - "U1070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1070"
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка NMAKE U1070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

циклическая зависимость в макроопределении "имя макроса"  
  
 Указанное макроопределение содержит макрос, в определении которого содержится оно само.  Циклическое определение макросов не допускается.  
  
## Пример  
 В приведенных ниже макроопределениях  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 возникает следующая ошибка:  
  
```  
cycle in macro definition 'TWO'  
```