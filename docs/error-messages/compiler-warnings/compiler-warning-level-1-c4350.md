---
title: "Предупреждение (уровень 1) C4350 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4350
dev_langs: C++
helpviewer_keywords: C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e05320bcfeac5ba340d286851e13439e53734a7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4350"></a>Предупреждение компилятора (уровень 1) C4350
изменение поведения: "член 1" был вызван вместо "член 2"  
  
 Не удается связать неконстантная ссылка rvalue. В версиях Visual C++ до Visual Studio 2003 можно было выполнить привязку rvalue неконстантная ссылка при прямой инициализации. Этот код выводит предупреждение.  
  
 Для обеспечения обратной совместимости по-прежнему можно выполнить привязку значений rvalue неконстантные ссылки, но стандартные преобразования являются предпочтительными везде, где это возможно.  
  
 Это предупреждение представляет изменение поведения компилятора Visual C++ .NET 2002. Если параметр включен, это предупреждение может быть выведено и для правильного кода. Например, ему может быть присвоен при использовании **std::auto_ptr** шаблона класса.  
  
 При появлении этого предупреждения, проверьте код, чтобы выяснить, зависит от привязки значений rvalue к ссылкам на неконстантный. Добавления константы к ссылке или указать дополнительные перегрузка константной может устранить проблему.  
  
 Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Следующий пример приводит к возникновению ошибки C4350:  
  
```cpp  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead:  
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