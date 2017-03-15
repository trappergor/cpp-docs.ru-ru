---
title: "Ошибка компилятора C2803 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2803"
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operator оператор" должен иметь по крайней мере один формальный параметр типа класса  
  
 Перегруженный оператор не имеет параметра типа класса.  
  
 Необходимо передать по крайней мере один параметр по ссылке \(используя не указатель, а ссылки\) или по значению, что позволит использовать « \< B» \(a и B быть класса a типа\).  
  
 Если оба параметра были бы указателями, выполнялось бы простое сравнение адресов указателей без использования преобразования, определенного пользователем.  
  
 Следующий пример приводит к возникновению ошибки C2803:  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```