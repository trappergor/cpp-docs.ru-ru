---
title: "@InStr | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "@InStr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "@InStr symbol"
ms.assetid: 980d5b9f-2b88-4306-8955-df6cd2133e68
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# @InStr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Функцию макроса, которая ищет первое вхождение *string2* IN *string1*, начиная с *положение* в рамках *string1*.  If *положение* не появляется, поиск начинается в начале *string1*.  Возвращает целое число или 0, если позиции *string2* не найдены.  
  
## Синтаксис  
  
```  
  
@InStr( [[position]], string1, string2 )  
```  
  
## См. также  
 [Symbols Reference](../../assembler/masm/symbols-reference.md)