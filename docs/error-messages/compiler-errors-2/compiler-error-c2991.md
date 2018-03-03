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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91bcca77639e07aa58d212df7e090dd88b7ad8ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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