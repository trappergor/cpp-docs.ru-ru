---
title: "Предупреждение (уровень 1) C4350 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c3a5411475d898562b8cba62ddeffcaf1dfec095
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4350"></a>Предупреждение компилятора (уровень 1) C4350
изменение поведения: "член&1;" был вызван вместо "член&2;"  
  
 Значение rvalue не может быть привязана неконстантной ссылку. В предыдущих версиях Visual C++ было возможно привязывать rvalue на ссылку неконстантной при прямой инициализации. Этот код выводит предупреждение.  
  
 Для обеспечения обратной совместимости по-прежнему можно выполнить привязку значений rvalue неконстантные ссылки, но стандартные преобразования являются предпочтительными везде, где это возможно.  
  
 Это предупреждение представляет изменение поведения в компиляторе Visual C++ .NET 2002. Если параметр включен, это предупреждение может быть выведено и для правильного кода. Например, он может предоставлять при использовании **std::auto_ptr** шаблона класса.  
  
 Если получено это предупреждение, проверьте код на наличие зависит от привязки значений rvalue к ссылкам неконстантной. Добавления константы к ссылке или предоставления дополнительной перегрузки константной может устранить проблему.  
  
 Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [компилятора предупреждения, — это отключение по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Следующий пример приводит к возникновению ошибки C4350:  
  
```  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```
