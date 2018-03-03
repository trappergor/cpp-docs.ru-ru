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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ae7349cce7e824af5621fba121e762aeccffa9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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