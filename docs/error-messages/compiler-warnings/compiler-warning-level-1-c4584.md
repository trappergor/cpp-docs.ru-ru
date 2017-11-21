---
title: "Предупреждение (уровень 1) C4584 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4584
dev_langs: C++
helpviewer_keywords: C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1c17d8871d16cd2eec6b46e01d9c1779f3440398
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4584"></a>Предупреждение компилятора (уровень 1) C4584
«класс1»: базовый класс «класс 2» уже является базовым классом «class3»  
  
 Определенный класс наследуется от двух классов, один из которых наследуется от другого. Пример:  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 В этом случае будет выдано предупреждение для класса C, так как он наследуется как от классов A и B, который наследует от класса а. Это предупреждение служит для напоминания, необходимо указывать полное использование членов базового класса, или создается ошибка компилятора из-за неоднозначности, обратитесь к члену класса.