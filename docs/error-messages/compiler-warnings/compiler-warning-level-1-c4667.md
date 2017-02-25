---
title: "Предупреждение компилятора (уровень 1) C4667 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4667"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4667"
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4667
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": не определено ни одной функции\-шаблона, которая бы соответствовала принудительному созданию экземпляра  
  
 Нельзя создать экземпляр необъявленного шаблона функции.  
  
 Следующий пример вызывает ошибку C4667:  
  
```  
// C4667a.cpp  
// compile with: /LD /W1  
template  
void max(const int &, const int &); // C4667 expected  
```  
  
 Чтобы разрешить данное предупреждение, следует сначала объявить шаблон функции:  
  
```  
// C4667b.cpp  
// compile with: /LD  
// Declare the function template  
template<typename T>  
const T &max(const T &a, const T &b) {  
   return (a > b) ? a : b;  
}  
// Then forcibly instantiate it with a desired type ... i.e. 'int'  
//  
template  
const int &max(const int &, const int &);  
```