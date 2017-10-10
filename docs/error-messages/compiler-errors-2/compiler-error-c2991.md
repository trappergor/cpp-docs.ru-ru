---
title: "Ошибка компилятора C2991 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2991
dev_langs:
- C++
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 44854e546449fe03457b7adc310abc36d1ce51f7
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2991"></a>Ошибка компилятора C2991
переопределение параметра типа "параметр"  
  
 Произошел конфликт типов между двумя определениями универсальных параметров или параметров шаблона `parameter`. При определении нескольких универсальных параметров или параметров шаблона необходимо использовать эквивалентные типы.  
  
 Следующий пример приводит к возникновению ошибки C2991:  
  
```  
// C2991.cpp  
// compile with: /c  
template<class T, class T> struct TC {};   // C2991  
// try the following line instead  
// template<class T, class T2> struct TC {};  
```  
  
 Ошибка C2991 также может возникнуть при использовании универсальных шаблонов.  
  
```  
// C2991b.cpp  
// compile with: /clr /c  
generic<class T,class T> ref struct GC {};   // C2991  
// try the following line instead  
// generic<class T,class T2> ref struct GC {};  
```
