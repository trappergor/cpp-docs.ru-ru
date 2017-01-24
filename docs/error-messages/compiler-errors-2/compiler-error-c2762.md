---
title: "Ошибка компилятора C2762 | Microsoft Docs"
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
  - "C2762"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2762"
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2762
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": недопустимое выражение в качестве аргумента шаблона для "аргумент"  
  
 При использовании параметра компиляции [\/Za](../../build/reference/za-ze-disable-language-extensions.md) преобразование целочисленного значения в указатель не выполняется.  
  
 Следующий пример приводит к возникновению ошибки C2762:  
  
```  
// C2762.cpp  
// compile with: /Za  
template<typename T, T *pT>  
class X2 {};  
  
void f2() {  
   X2<int, 0> x21;   // C2762  
   // try the following line instead  
   // X2<int, static_cast<int *>(0)> x22;  
}  
```