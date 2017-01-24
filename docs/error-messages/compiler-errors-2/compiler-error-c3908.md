---
title: "Ошибка компилятора C3908 | Microsoft Docs"
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
  - "C3908"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3908"
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3908
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

уровень доступа менее строгий, чем "конструкция"  
  
 Метод доступа к свойству \(вернуть или задать\) не может иметь менее строгое ограничение, чем доступ, указанный в самом свойстве.  То же относится к методам доступа к событию.  
  
 Дополнительные сведения см. в описании [свойства](../../windows/property-cpp-component-extensions.md) и [события](../../windows/event-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3908:  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```