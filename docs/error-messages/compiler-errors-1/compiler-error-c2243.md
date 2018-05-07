---
title: Ошибка компилятора C2243 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16bc95540488b0723869c735b7fc80b15f6e763b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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