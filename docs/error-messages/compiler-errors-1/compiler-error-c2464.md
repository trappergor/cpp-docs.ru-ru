---
title: "Ошибка компилятора C2464 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2464"
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2464
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": невозможно использовать "new" для выделения памяти для ссылки  
  
 Память для идентификатора ссылки выделена с помощью оператора `new`.  Ссылки не являются объектами памяти, поэтому оператор `new` не может вернуть указатель на них.  Для объявления ссылки воспользуйтесь стандартным синтаксисом объявления переменной.  
  
 Следующий пример приводит к возникновению ошибки C2464:  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```