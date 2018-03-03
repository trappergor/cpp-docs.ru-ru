---
title: "Ошибка компилятора C2804 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2804
dev_langs:
- C++
helpviewer_keywords:
- C2804
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d6dd8bb7afe1416739d9ee4c889d0d850778b09
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2804"></a>Ошибка компилятора C2804
бинарный оператор operator имеет слишком много параметров  
  
 Перегруженная функция-член бинарного оператора объявлена более чем с одним параметром. Подразумевается первый операнд функции-члена бинарного оператора, типом которого является включающий тип оператор.  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C2804 и приводятся сведения по ее устранению.  
  
```  
// C2804.cpp  
// compile by using: cl /c /W4 C2804.cpp  
class X {  
public:  
   X& operator+= (const X &left, const X &right);   // C2804  
   X& operator+= (const X &right);   // OK - left operand implicitly *this  
};  
  
int main() {  
   X x, y;  
   x += y;   // equivalent to x.operator+=(y)  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C2804 и приводятся сведения по ее устранению.  
  
```  
// C2804_2.cpp  
// compile with: /clr /c  
ref struct Y {  
   Y^ operator +(Y^ hY, int i);   // C2804  
   static Y^ operator +(Y^ hY, int i);   // OK  
   Y^ operator +(int i);   // OK  
};  
```