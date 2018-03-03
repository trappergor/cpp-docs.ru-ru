---
title: "Предупреждение (уровень 3) C4534 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d9ea2cc6fb15edf61610e96a728e985b78be468
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4534"></a>Предупреждение компилятора (уровень 3) C4534
«конструктор» не будет конструктором по умолчанию для класса «класс» из-за аргумента по умолчанию  
  
 Неуправляемый класс может иметь конструктор с параметрами, имеющими значения по умолчанию, и компилятор будет использоваться как конструктор по умолчанию. Класс, помеченный `value` ключевое слово не будет использовать конструктор со значениями по умолчанию для параметров как конструктор по умолчанию.  
  
 Дополнительные сведения см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C4534:  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```