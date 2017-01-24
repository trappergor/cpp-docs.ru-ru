---
title: "Ошибка компилятора C3672 | Microsoft Docs"
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
  - "C3672"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3672"
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3672
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

выражение псевдо\-деструктора можно использовать только как часть вызова функции  
  
 Некорректный вызов деструктора.  Для получения дополнительной информации см. [Деструкторы](../../cpp/destructors-cpp.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3672.  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```