---
title: Ошибка компилятора C3290 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3290
dev_langs:
- C++
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf65a35469ca978b0464c6f7275a6ac0e331da5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3290"></a>Ошибка компилятора C3290
"тип": тривиальное свойство не может иметь ссылочный тип  
  
 Свойство объявлено неправильно. При объявлении обычного свойства компилятор создает переменную, которую будет обновлять свойство. В классе не может присутствовать ссылочная переменная с отслеживанием.  
  
 В разделе [свойство](../../windows/property-cpp-component-extensions.md) и [оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3290:  
  
```  
// C3290.cpp  
// compile with: /clr /c  
ref struct R {};  
  
ref struct X {  
   R^ mr;  
  
   property R % y;   // C3290  
   property R ^ x;   // OK  
  
   // OK  
   property R% prop {  
      R% get() {   
         return *mr;   
      }  
  
      void set(R%) {}  
   }  
};  
  
int main() {  
   X x;  
   R% xp = x.prop;  
}  
```