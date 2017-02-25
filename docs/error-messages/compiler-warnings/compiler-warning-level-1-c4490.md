---
title: "Предупреждение компилятора (уровень 1) C4490 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4490"
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Предупреждение компилятора (уровень 1) C4490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переопределение": неправильное использование спецификатора переопределения; "функция" не соответствует методу базового класса\-ссылки  
  
 Спецификатор переопределения был использован неправильно.  Например, функция интерфейса была не переопределена, а реализована.  
  
 Для получения дополнительной информации см. [Спецификаторы переопределения](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере возникает предупреждение C4490.  
  
```  
// C4490.cpp  
// compile with: /clr /c /W1  
  
interface struct IFace {  
   void Test();  
};  
  
ref struct Class1 : public IFace {  
   virtual void Test() override {}   // C4490  
   // try the following line instead  
   // virtual void Test() {}  
};  
```