---
title: "Ошибка компилятора C2061 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 82518c78b49418c10cc0cd07ae59e58336af08f3
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2061"></a>Ошибка компилятора C2061
Синтаксическая ошибка: идентификатор «идентификатор»  
  
 Компилятор обнаружил идентификатор, где он не ожидался. Убедитесь, что `identifier` объявлена, прежде чем использовать его.  
  
 Инициализатор могут быть заключены в круглые скобки. Чтобы избежать этой проблемы, заключите декларатор в круглые скобки или сделайте его `typedef`.  
  
 Эта ошибка также может быть вызвано, если компилятор определяет выражение как аргумент шаблона класса; Используйте [typename](../../cpp/typename.md) для сообщает компилятору, что он является типом.  
  
 Следующий пример приводит к возникновению ошибки C2061:  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 может возникать, если передать имя экземпляра для [typeid](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```
