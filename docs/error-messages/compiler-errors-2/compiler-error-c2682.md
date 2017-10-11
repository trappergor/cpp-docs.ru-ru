---
title: "Ошибка компилятора C2682 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2682
dev_langs:
- C++
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3df494f5d78a862e260fa4edfe0a2740e4fc8cdd
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2682"></a>Ошибка компилятора C2682
Невозможно использовать "оператор приведения" для преобразования из «тип1» в «тип2»  
  
 Оператор приведения предпринял попытку преобразования между двумя несовместимыми типами. Например, нельзя использовать [dynamic_cast](../../cpp/dynamic-cast-operator.md) оператор для преобразования указателя в ссылку. `dynamic_cast` Оператор не может использоваться для снятия квалификаторов. Все квалификаторы типов должны совпадать.  
  
 Можно использовать `const_cast` оператор, удалите атрибуты, такие как `const`, `volatile`, или `__unaligned`.  
  
 Следующий пример приводит к возникновению ошибки C2682:  
  
```  
// C2682.cpp  
class A { virtual void f(); };  
class B: public A {};  
  
void g(A* pa) {  
    B& rb = dynamic_cast<B&>(pa); // C2682  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C2682:  
  
```  
// C2682b.cpp  
// compile with: /clr  
ref struct R{};  
ref struct RR : public R{};  
ref struct H {  
   RR^ r ;  
   short s;  
   int i;  
};  
  
int main() {  
   H^ h = gcnew H();    
   interior_ptr<int>lr = &(h->i);  
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682  
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK  
}  
```
