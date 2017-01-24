---
title: "Предупреждение компилятора (уровень 1) C4489 | Microsoft Docs"
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
  - "C4489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4489"
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"спецификатор": не разрешен в методе интерфейса "метод"; переопределите спецификаторы, которые разрешены только для ссылочного класса и методов классов значений  
  
 Неправильно использовано ключевое слово спецификатора для метода интерфейса.  
  
 Для получения дополнительной информации см. [Спецификаторы переопределения](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере показано возникновение ошибки C4489.  
  
```  
// C4489.cpp  
// compile with: /clr /c /W1  
public interface class I {   
   void f() new;   // C4489  
   virtual void b() override;   // C4489  
  
   void g();   // OK  
};  
```