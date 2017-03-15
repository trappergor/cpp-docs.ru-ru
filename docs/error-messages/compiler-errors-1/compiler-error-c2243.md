---
title: "Ошибка компилятора C2243 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2243"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2243"
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2243
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразование conversion type из type1 в type2 существует, но недоступно  
  
 Защита доступа \(`protected` или `private`\) не позволила выполнить преобразование из указателя на производный класс в указатель на базовый класс.  
  
 Следующий пример приводит к возникновению ошибки C2243:  
  
```  
// C2243.cpp  
// compile with: /c  
class B {};  
class D : private B {};  
class E : public B {};  
  
D d;  
B *p = &d;   // C2243  
  
E e;  
B *p2 = &e;  
```  
  
 Базовые классы с типом доступа `protected` или `private` недоступны клиентам производного класса.  Эти уровни контроля доступа используются для обозначения того, что базовый класс в реализации должен быть невидим для клиентов.  Используйте открытое наследование, чтобы у клиентов производного класса был доступ к неявному преобразованию указателя на производный класс в указатель на базовый класс.