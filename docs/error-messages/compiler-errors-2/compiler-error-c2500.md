---
title: "Ошибка компилятора C2500 | Microsoft Docs"
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
  - "C2500"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2500"
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2500
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор 1": "идентификатор 2" уже является прямым базовым классом  
  
 Класс или структура появляются в списке базовых классов более одного раза.  
  
 Прямым базовым классом является класс, упомянутый в основном списке базовых классов.  Косвенным базовым классом считается базовый класс одного из классов основного списка.  
  
 Нельзя более одного раза указать класс как прямой базовый класс.  Класс можно более одного раза использовать как косвенный базовый класс.  
  
 Следующий пример приводит к возникновению ошибки C2500:  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```