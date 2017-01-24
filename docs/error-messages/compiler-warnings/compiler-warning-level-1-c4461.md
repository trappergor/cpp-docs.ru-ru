---
title: "Предупреждение компилятора (уровень 1) C4461 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4461"
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"type" : данный класс имеет метод завершения "finalizer", но не имеет деструктора "dtor"  
  
 Присутствие метода завершения в типе обозначает удаление ресурсов.  До тех пор пока метод завершения явно не вызывается из деструктора типа, среда CLR определяет время запуска метода завершения после того, как объект выходит из области.  
  
 Если деструктор определяется в типе и явно вызывает метод завершения из метода разрушения, есть возможность определенно использовать метод завершения.  
  
 Дополнительные сведения см. в разделе [Деструкторы и завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## Пример  
 В следующем примере формируется сообщение об ошибке С4461.  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```