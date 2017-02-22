---
title: "Ошибка компилятора ресурсов RC2148 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2148"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2148"
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора ресурсов RC2148
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком большой идентификатор SUBLANGUAGE  
  
 Значение идентификатора SUBLANGUAGE ID вышло за пределы диапазона.  
  
 Оператор **LANGUAGE** должен использовать следующий синтаксис:  
  
 **LANGUAGE** *primary\_language\_ID*,*secondary\_language\_ID*  
  
 Допустимые значения идентификатора SUBLANGUAGE определяются как константы **SUBLANG\_** в файле WINNT.h.