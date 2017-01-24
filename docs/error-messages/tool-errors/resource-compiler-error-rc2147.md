---
title: "Ошибка компилятора ресурсов RC2147 | Microsoft Docs"
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
  - "RC2147"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2147"
ms.assetid: 09974f06-1731-4e70-b373-f9218e0ee8d9
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора ресурсов RC2147
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

идентификатор SUBLANGUAGE не является числом  
  
 Значение идентификатора SUBLANGUAGE должно быть числом.  
  
 Оператор **LANGUAGE** должен использовать следующий синтаксис:  
  
 **LANGUAGE** *primary\_language\_ID*,*secondary\_language\_ID*  
  
 Допустимые значения идентификатора SUBLANGUAGE определяются как константы **SUBLANG\_** в файле WINNT.h.