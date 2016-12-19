---
title: "Ошибка компилятора C2569 | Microsoft Docs"
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
  - "C2569"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2569"
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2569
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"EnumOrUnion" : перечисление или объединение невозможно использовать в качестве базового класса  
  
 Если необходимо получить тип, производный от указанного объединения или перечисления, замените объединение или перечисление на класс или структуру.  
  
 Следующий пример приводит к возникновению ошибки C2569:  
  
```  
// C2569.cpp  
// compile with: /c  
union ubase {};  
class cHasPubUBase : public ubase {};   // C2569  
// OK  
struct sbase {};  
class cHasPubUBase : public sbase {};  
```