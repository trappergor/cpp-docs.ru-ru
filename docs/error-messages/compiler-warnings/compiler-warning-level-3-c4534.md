---
title: Предупреждение (уровень 3) C4534 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b765f5f654c8d533b0ae22d874e7657cd10d667
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293037"
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