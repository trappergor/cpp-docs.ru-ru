---
title: "Ошибка компилятора C2632 | Microsoft Docs"
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
  - "C2632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2632"
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1', следующий за типом 'type2', недопустим  
  
 Эта ошибка может возникать, если утрачен код между двумя спецификаторами.  
  
 Следующий пример приводит к возникновению ошибки C2632:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Это ошибка также может возникать в результате работ по стандартизации компилятора, выполненных для Visual Studio .NET 2003.  `bool` теперь является правильным типом.  В предыдущих версиях `bool` был определением, и можно было создать идентификаторы с именем.  
  
 Следующий пример приводит к возникновению ошибки C2632:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Чтобы устранить эту ошибку так, чтобы код был допустимым и в Visual Studio .NET 2003, и в Visual Studio .NET Visual C\+\+, переименуйте идентификатор.