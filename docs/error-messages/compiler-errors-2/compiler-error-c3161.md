---
title: "Ошибка компилятора C3161 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3161"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3161"
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3161
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"interface" : вложенный класс, структура, объединение или интерфейс в интерфейсе недопустимы; вложенный в класс интерфейс, структура или объединение недопустимы.  
  
 [\_\_interface](../Topic/__interface.md) может появиться только в глобальной области видимости.  Класс, структура или объединение не могут появляться в интерфейсе.  
  
## Пример  
 В следующем примере формируется сообщение об ошибке C3161.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```