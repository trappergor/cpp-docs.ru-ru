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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a7be7320c21469536f6ddada99abd862812d882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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