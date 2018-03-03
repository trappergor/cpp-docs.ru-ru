---
title: "Ошибка компилятора C2079 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2079
dev_langs:
- C++
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9eb8dda8af6a71cda1d3a4f9114af238110afc01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2079"></a>Ошибка компилятора C2079
«Идентификатор» использует неопределенный класса, структуры или объединения «имя»  
  
 Указанный идентификатор является неопределенным класса, структуры или объединения.  
  
 Эта ошибка может быть вызвана инициализация анонимного объединения.  
  
 Следующий пример приводит к возникновению ошибки C2079:  
  
```  
// C2079.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   std::ifstream g;   // C2079  
}  
```  
  
 Возможное решение  
  
```  
// C2079b.cpp  
// compile with: /EHsc  
#include <fstream>  
int main( ) {  
   std::ifstream g;  
}  
```  
  
 C2079 также может возникать при попытке объявления объекта в стеке типы, у которого опережающего объявления только в области.  
  
```  
// C2079c.cpp  
class A;  
  
class B {  
   A a;   // C2079  
};  
  
class A {};  
```  
  
 Возможное решение  
  
```  
// C2079d.cpp  
// compile with: /c  
class A;  
class C {};  
  
class B {  
   A * a;  
   C c;  
};  
  
class A {};  
```