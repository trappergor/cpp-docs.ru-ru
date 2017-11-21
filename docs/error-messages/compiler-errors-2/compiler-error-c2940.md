---
title: "Ошибка компилятора C2940 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2940
dev_langs: C++
helpviewer_keywords: C2940
ms.assetid: af6bf2bf-8de6-4cfd-bbf0-4c6b32a30edf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7091feef6c5cdb41a8b8cbfe661daa96f2eb21cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2940"></a>Ошибка компилятора C2940
"класс": идентификатор класса типа переопределен как локальное определение типа (typedef)  
  
 Универсальный класс или класс шаблона нельзя использовать в качестве локального `typedef`.  
  
 Следующий пример приводит к возникновению ошибки C2940:  
  
```  
// C2940.cpp  
template<class T>  
struct TC {};   
int main() {  
   typedef int TC<int>;   // C2940  
   typedef int TC;   // OK  
}  
```  
  
 Ошибка C2940 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2940b.cpp  
// compile with: /clr  
generic<class T>  
ref struct GC { };  
  
int main() {  
   typedef int GC<int>;   // C2940  
   typedef int GC;  
}  
```