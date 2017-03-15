---
title: "Ошибка компилятора C2870 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2870"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2870"
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2870
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя": определение пространства имен должно делаться на уровне файла или непосредственно в другом определении пространства имен  
  
 Недопустимое объявление пространства имен `name`.  Определение пространства имен должно выполняться на уровне файла \(вне любых блоков и классов\) или непосредственно в другом пространстве имен.  
  
 Следующий пример приводит к возникновению ошибки C2870:  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```