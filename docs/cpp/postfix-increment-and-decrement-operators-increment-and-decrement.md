---
title: "Постфиксные операторы увеличения и уменьшения: ++ и--| Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs: C++
helpviewer_keywords:
- increment operators [C++], syntax
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e1d6c13da3023073f3d8b3e9625fa141253ba2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Постфиксные операторы увеличения и уменьшения ++ и --
## <a name="syntax"></a>Синтаксис  
  
```  
postfix-expression ++  
postfix-expression --  
```  
  
## <a name="remarks"></a>Примечания  
 В C++ доступны префиксные и постфиксные операции инкремента и декремента. В этом разделе описываются только их постфиксные формы. (Дополнительные сведения см. в разделе [префикса инкремента и декремента](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) Различие между ними — в том, что в постфиксной записи оператор находится после *Постфиксное выражение*, тогда как в префиксной записи он располагается перед *выражение.* В следующем примере представлен постфиксный оператор инкремента:  
  
```  
i++;  
```  
  
 В результате применения постфиксного оператора инкремента (`++`) значение операнда увеличивается на одну единицу соответствующего типа. Аналогичным образом, в результате применения постфиксного оператора декремента (**--**) значение операнда уменьшается на одну единицу соответствующего типа.  
  
 Важно отметить, что в постфиксной операции инкремента или декремента выражение для вычисления значения выражения **до** применения соответствующего оператора. Операция инкремента или декремента выполняется **после** операнд вычисляется. Эта особенность возникает, только когда постфиксная операция инкремента или декремента выполняется в контексте выражения.  
  
 Если же постфиксный оператор применяется к аргументу функции, то инкремент или декремент значения аргумента необязательно будет выполнен до его передачи в функцию.  Дополнительные сведения см. в разделе 1.9.17 стандарта C++.  
  
 Применения постфиксного оператора инкремента к указателю на массив объектов типа **длинные** фактически прибавляется 4 внутреннее представление указателя. Это приводит к возникновению указатель, который раньше относился  *n* й элемент массива, для обращения к (*n*+ 1) элемент th.  
  
 Операнды для постфиксных операторов декремента должны иметь изменяемые (не **const**) l значения арифметического или указательного типа. Тип результата — так же, как *Постфиксное выражение*, но больше не является l значением.  
  
**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Операнд постфиксного оператора инкремента или декремента не может быть типа `bool`.
  
 Ниже показан пример постфиксного оператора инкремента.  
  
```  
// expre_Postfix_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 10;  
   cout << i++ << endl;  
   cout << i << endl;  
}  
```  
  
 Постфиксные операции инкремента или декремента для типов перечисления не поддерживаются:  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## <a name="see-also"></a>См. также  
 [Постфиксные выражения](../cpp/postfix-expressions.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Постфиксные операторы увеличения и уменьшения в C](../c-language/c-postfix-increment-and-decrement-operators.md)