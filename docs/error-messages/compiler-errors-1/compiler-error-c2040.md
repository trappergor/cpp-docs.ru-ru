---
title: "Ошибка компилятора C2040 | Microsoft Docs"
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
  - "C2040"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2040"
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2040
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

operator: identifier1 отличается по уровням косвенного обращения от identifier2  
  
 Выражение, включающее заданные операнды, содержит несовместимые или неявно преобразованные типы операндов.  Если оба операнда арифметические или неарифметические \(например, массив или указатель\), они используются без изменения.  Если один из операндов арифметический, а другой — нет, арифметический операнд преобразуется в неарифметический.  
  
 В этом примере показано возникновение ошибки C2040 и приводятся сведения по ее устранению.  
  
```  
// C2040.cpp  
// Compile by using: cl /c /W3 C2040.cpp  
bool test() {  
   char c = '3';  
   return c == "3"; // C2446, C2040  
   // return c == '3'; // OK  
}  
  
```