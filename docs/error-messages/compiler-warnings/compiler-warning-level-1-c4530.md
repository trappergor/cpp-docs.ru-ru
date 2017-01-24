---
title: "Предупреждение компилятора (уровень 1) C4530 | Microsoft Docs"
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
  - "C4530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4530"
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Использован обработчик исключений C\+\+, но семантика уничтожения объектов не включена.Задайте параметр \/EHsc  
  
 Была использована обработка исключений C\+\+, однако параметр [\/EHsc](../../build/reference/eh-exception-handling-model.md) не был выбран.  
  
 Если параметр \/EHsc не был включен, объект, автоматически сохраняемый во фрейме между функцией, выполняющей оператор throw, и функцией, перехватывающей оператор throw, не уничтожается.  Однако автоматически сохраняемый объект, созданный в блоке **try** или **catch**, уничтожается.  
  
 Следующий пример приводит к возникновению ошибки C4530:  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Скомпилируйте пример с параметром \/EHsc, чтобы устранить предупреждение.