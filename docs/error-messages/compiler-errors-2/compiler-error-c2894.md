---
title: "Ошибка компилятора C2894 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2894
dev_langs: C++
helpviewer_keywords: C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b07a486e02a1592fe43a56d63bcbea3fb3971ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2894"></a>Ошибка компилятора C2894
шаблоны не могут объявляться компоновку «C»  
  
 Эта ошибка может быть вызвана шаблона, определенного в `extern` блок «C».  
  
 Следующий пример приводит к возникновению ошибки C2894:  
  
```  
// C2894.cpp  
extern "C" {  
   template<class T> class stack {};   // C2894 fail  
  
   template<class T> void f(const T &aT) {}   // C2894  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C2894:  
  
```  
// C2894b.cpp  
// compile with: /c  
extern "C" template<class T> void f(const T &aT) {}   // C2894  
  
template<class T> void f2(const T &aT) {}   // OK  
```