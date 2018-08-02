---
title: 'Постфиксные операторы увеличения и уменьшения: ++ и--| Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1a878fe1c18889c1abfef995786ffcc9a267981
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404058"
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Постфиксные операторы увеличения и уменьшения ++ и --
## <a name="syntax"></a>Синтаксис  
  
```  
postfix-expression ++  
postfix-expression --  
```  
  
## <a name="remarks"></a>Примечания  
 В C++ доступны префиксные и постфиксные операции инкремента и декремента. В этом разделе описываются только их постфиксные формы. (Дополнительные сведения см. в разделе [операторы префикса увеличения и уменьшения](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) Различие между ними — что в постфиксной записи оператор находится после *Постфиксное выражение*, тогда как в префиксной записи он располагается перед *выражение.* В следующем примере представлен постфиксный оператор инкремента:  
  
```cpp 
i++;  
```  
  
 В результате применения постфиксного оператора инкремента (**++**) — что значение операнда увеличивается на одну единицу соответствующего типа. Аналогичным образом, в результате применения постфиксного оператора декремента (**--**) — что значение операнда уменьшается на одну единицу соответствующего типа.  
  
 Важно отметить, что в постфиксной операции инкремента или декремента выражение значение выражения *до* применения соответствующего оператора. Операция инкремента или декремента выполняется *после* операнд вычисляется. Эта особенность возникает, только когда постфиксная операция инкремента или декремента выполняется в контексте выражения.  
  
 Если же постфиксный оператор применяется к аргументу функции, то инкремент или декремент значения аргумента необязательно будет выполнен до его передачи в функцию.  Дополнительные сведения см. в разделе 1.9.17 стандарта C++.  
  
 Применения постфиксного оператора инкремента к указателю на массив объектов типа **long** фактически добавляет четыре внутреннего представления указателя. В результате этого указатель, который раньше относился *n*-й элемент массива, для ссылки на (*n*+ 1) элемент th.  
  
 Операнды для постфиксных инкремента и Постфиксные операторы декремента должны иметь изменяемые (не **const**) l значения арифметического или указательного типа. Тип результата совпадает со значением, *Постфиксное выражение*, но больше не является l значением.  
  
**Visual Studio 2017 версии 15.3 и более поздние версии** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Операнд постфиксного оператора инкремента или декремента не может быть типа **bool**.
  
 Ниже показан пример постфиксного оператора инкремента.  
  
```cpp 
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
  
```cpp 
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## <a name="see-also"></a>См. также  
 [Постфиксные выражения](../cpp/postfix-expressions.md)   
 [Встроенные операторы C++, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Постфиксные операторы увеличения и уменьшения в C](../c-language/c-postfix-increment-and-decrement-operators.md)