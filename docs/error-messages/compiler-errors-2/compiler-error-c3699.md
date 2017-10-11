---
title: "Ошибка компилятора C3699 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3699
dev_langs:
- C++
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: caabe5d8d9e956081211ef23546f0d720ecdcbd6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3699"></a>Ошибка компилятора C3699
«оператор»: невозможно использовать этот косвенный оператор для типа «тип»  
  
 Была предпринята попытка использовать косвенный оператор, не разрешен в `type`.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3699.  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## <a name="example"></a>Пример  
 Тривиальное свойство не может иметь ссылочный тип. Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) . Следующий пример приводит к возникновению ошибки C3699.  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## <a name="example"></a>Пример  
 Эквивалентом синтаксиса «указатель на указатель» представляет собой дескриптор для отслеживания ссылок. Следующий пример приводит к возникновению ошибки C3699.  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```
