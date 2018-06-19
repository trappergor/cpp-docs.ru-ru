---
title: Ошибка компилятора C2500 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c05ffd59e415375dd3c7f94ae9bc377c0fc2b9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229226"
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