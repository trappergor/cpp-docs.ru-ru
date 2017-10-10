---
title: "Ошибка компилятора C2500 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2b869ca0ba959e9b774a005298ef4456d0995156
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2500"></a>Ошибка компилятора C2500
«идентификатор1»: «идентификатор2» уже является прямым базовым классом  
  
 Класс или структура появляется более одного раза в списке базовых классов.  
  
 Прямым базовым классом является упомянутый в базовый список. Косвенным базовым классом считается базовый класс одного из классов в базовый список.  
  
 Класс не указан более одного раза от прямого базового класса. Класс можно использовать как косвенный базовый класс более одного раза.  
  
 Следующий пример приводит к возникновению ошибки C2500:  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```
