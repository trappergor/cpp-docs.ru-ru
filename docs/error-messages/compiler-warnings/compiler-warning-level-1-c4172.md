---
title: "Предупреждение компилятора (уровень 1) C4172 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4172"
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

возвращение адреса локальной или временной переменной  
  
 Функция возвращает адрес локальной переменной или временного объекта.  Локальные переменные и временные объекты уничтожаются по завершении выполнения функции, поэтому возвращаемый адрес является недействительным.  
  
 Измените функцию так, чтобы она не возвращала адрес локального объекта.  
  
 Следующий пример приводит к возникновению ошибки C4172:  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```