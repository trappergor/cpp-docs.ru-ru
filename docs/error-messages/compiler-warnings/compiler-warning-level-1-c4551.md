---
title: "Предупреждение компилятора (уровень 1) C4551 | Microsoft Docs"
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
  - "C4551"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4551"
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4551
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

в вызове функции отсутствует список аргументов  
  
 Вызов функции должен включать открывающие и закрывающие круглые скобки после имени функции, даже если функция не принимает параметры.  
  
 Следующий пример приводит к возникновению ошибки C4551:  
  
```  
// C4551.cpp  
// compile with: /W1  
void function1() {  
}  
  
int main() {  
   function1;   // C4551  
   function1();   // OK  
}  
```