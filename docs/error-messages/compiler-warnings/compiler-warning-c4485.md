---
title: "Предупреждение компилятора C4485 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4485
dev_langs:
- C++
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 435e49a857e3c448ac7e5f7ef00bb9032320aa25
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4485"></a>Предупреждение компилятора C4485
«переопределяющая_функция»: соответствует методу базового класса «базового класса», но не помеченные «new» или «override»; предполагается «new» (и «virtual»)  
  
 Переопределяет метод доступа, независимо от `virtual` ключевое слово, функцию доступа базового класса, но `override` или `new` описатель не является частью подписи переопределяющей функции. Добавить `new` или `override` описатель, чтобы устранить это предупреждение.  
  
 В разделе [переопределить](../../windows/override-cpp-component-extensions.md) и [new (новый слот в vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md) для получения дополнительной информации.  
  
 C4485 всегда выдается как ошибка. Используйте [предупреждение](../../preprocessor/warning.md) pragma, чтобы отключить предупреждение C4485.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4485  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```
