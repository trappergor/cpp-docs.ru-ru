---
title: "Ошибка компилятора C2243 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d9725239c7e7b8899c23584aa56d26ed77bd757a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2243"></a>Ошибка компилятора C2243
Преобразование conversion type из type1 в type2 существует, но недоступно  
  
 Защита доступа (`protected` или `private`) не позволила выполнить преобразование из указателя на производный класс в указатель на базовый класс.  
  
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
  
 Базовые классы с типом доступа `protected` или `private` недоступны клиентам производного класса. Эти уровни контроля доступа используются для обозначения того, что базовый класс в реализации должен быть невидим для клиентов. Используйте открытое наследование, чтобы у клиентов производного класса был доступ к неявному преобразованию указателя на производный класс в указатель на базовый класс.
