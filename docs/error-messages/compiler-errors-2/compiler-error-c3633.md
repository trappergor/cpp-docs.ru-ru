---
title: "Ошибка компилятора C3633 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3633
dev_langs:
- C++
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 982075cdaa72ddd5b1a4fdafdeaaf433b27bcf77
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3633"></a>Ошибка компилятора C3633
не удается определить «член» в качестве члена управляемого «тип»  
  
Члены данных среды CLR ссылочного класса не может иметь тип POD C++.  Можно создать только машинного типа POD в тип CLR.  Например тип POD не может содержать конструктор копии или оператор присваивания.  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3633.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  

