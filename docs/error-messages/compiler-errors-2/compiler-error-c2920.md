---
title: "Ошибка компилятора ошибка C2920 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: acce1076abd47f86ccad7cf0b94c4cb11f28bd18
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2920"></a>Ошибка компилятора C2920
переопределение: class: шаблон класса или универсальный тип уже объявлен type  
  
 Универсальный класс или класс-шаблон имеет несколько объявлений, которые не эквивалентны. Чтобы устранить эту ошибку, используйте разные имена для различных типов или удалите переопределение имени типа.  
  
 В следующем примере показано возникновение ошибки C2920 и приводятся сведения по ее устранению.  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 Ошибка C2920 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
```
