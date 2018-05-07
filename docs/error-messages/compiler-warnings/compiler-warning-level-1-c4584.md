---
title: Предупреждение (уровень 1) C4584 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df3f92142fe42451ca7ae8272463d9347a263121
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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