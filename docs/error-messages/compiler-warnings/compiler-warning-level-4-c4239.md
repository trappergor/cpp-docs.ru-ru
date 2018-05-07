---
title: Предупреждение (уровень 4) C4239 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4239
dev_langs:
- C++
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d756bba65100d3e5c2987527d7a0dd4cc3fdc050
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4239"></a>Предупреждение компилятора (уровень 4) C4239
использовано нестандартное расширение: «токен»: преобразование из «тип» в «тип»  
  
 Это преобразование типа не допускается стандартом C++, но разрешается здесь в качестве расширения. Это предупреждение всегда следует хотя бы одна строка с описанием нарушенного правила языка.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4239.  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## <a name="example"></a>Пример  
 Преобразование целочисленного типа в перечисляемый тип строго не допускается.  
  
 Следующий пример приводит к возникновению ошибки C4239.  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```