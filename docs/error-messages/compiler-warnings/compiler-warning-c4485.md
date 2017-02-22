---
title: "Предупреждение компилятора C4485 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4485"
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора C4485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"override\_function": соответствует методу "base\_class\_function" базового класса\-ссылки, но не помечен как "new" или "override"; предполагается "new" \(и "virtual"\)  
  
 Метод доступа переопределяет функцию доступа базового класса \(с ключевым словом `virtual` или без него\), однако спецификатор `override` или `new` не является частью подписи переопределяющей функции.  Для устранения предупреждения добавьте спецификатор `new` или `override`.  
  
 Дополнительные сведения см. в разделах [override](../../windows/override-cpp-component-extensions.md) и [new \(новый слот в vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
 Предупреждение C4485 всегда выводится в качестве ошибки.  Используйте директиву pragma[warning](../../preprocessor/warning.md), чтобы отключить предупреждение C4485.  
  
## Пример  
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