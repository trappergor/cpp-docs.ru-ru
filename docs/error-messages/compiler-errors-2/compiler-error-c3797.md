---
title: "Ошибка компилятора C3797 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3797"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3797"
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Ошибка компилятора C3797
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переопределение": объявление события не может содержать спецификатор переопределения \(он должен быть размещен в методах события add\/remove\/raise\)  
  
 Невозможно определить тривиальное событие \(событие, не имеющие явно определенных методов доступа\) с помощью другого тривиального события.  Переопределяющее событие должно определять поведение события с помощью функций доступа.  
  
 Для получения дополнительной информации см. [event](../../windows/event-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3797.  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```