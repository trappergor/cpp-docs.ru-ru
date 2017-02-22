---
title: "Ошибка компилятора C2061 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2061"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2061"
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Ошибка компилятора C2061
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

синтаксическая ошибка: идентификатор "идентификатор"  
  
 Компилятор находит идентификатор там, где он не ожидался.  Убедитесь, что `identifier` объявлен перед использованием.  
  
 Инициализатор может быть заключен в круглые скобки.  Чтобы избежать этой проблемы, заключите декларатор в круглые скобки или сделайте его `typedef`.  
  
 Эта ошибка может также быть вызвана, когда компилятор определяет выражение как аргумент шаблона класса; используйте [имя типа](../Topic/typename.md) для того, чтобы сообщить компилятору его тип.  
  
 Следующий пример приводит к возникновению ошибки C2061:  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 может возникать, если [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) было передано имя экземпляра.  
  
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