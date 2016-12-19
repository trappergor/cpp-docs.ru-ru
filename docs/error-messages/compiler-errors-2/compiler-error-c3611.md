---
title: "Ошибка компилятора C3611 | Microsoft Docs"
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
  - "C3611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3611"
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": запечатанная функция не может иметь строгий спецификатор  
  
 Неправильно объявлена запечатанная функция.  Для получения дополнительной информации см. [запечатанные](../../windows/sealed-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере показано возникновение ошибки C3611.  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```