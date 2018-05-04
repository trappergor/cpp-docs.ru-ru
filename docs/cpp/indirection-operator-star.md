---
title: 'Оператор косвенного обращения: * | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d63fbe4042bb86f1ac7810302eeaa1b7978422b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="indirection-operator-"></a>Оператор косвенного обращения: *
## <a name="syntax"></a>Синтаксис  
  
```  
  
* cast-expression  
```  
  
## <a name="remarks"></a>Примечания  
 Унарный оператор косвенного обращения (**\***) разыменовывает указатель; то есть преобразует значение указателя в l значением. Операнд косвенного оператора должен быть указателем на тип. Результат косвенного выражения — тип, производным которого является тип указателя. Использование **\*** в этом контексте отличается от его значения как бинарного оператора, то есть умножения.  
  
 Если операнд указывает на функцию, результатом является указатель функции. Если он указывает на место хранения, результатом является l-значение, указывающее на место хранения.  
  
 Косвенный оператор может использоваться кумулятивно для разыменования указателей на указатели. Пример:  
  
```  
// expre_Indirection_Operator.cpp  
// compile with: /EHsc  
// Demonstrate indirection operator  
#include <iostream>  
using namespace std;  
int main() {  
   int n = 5;  
   int *pn = &n;  
   int **ppn = &pn;  
  
   cout  << "Value of n:\n"  
         << "direct value: " << n << endl  
         << "indirect value: " << *pn << endl  
         << "doubly indirect value: " << **ppn << endl  
         << "address of n: " << pn << endl  
         << "address of n via indirection: " << *ppn << endl;  
}  
```  
  
 Если значение указателя недопустимо, результат становится неопределенным. Ниже приведены наиболее распространенные условия, при которых значение указателя становится недопустимым.  
  
-   Указатель является пустым указателем.  
  
-   Указатель определяет адрес локального элемента, не видимого во время обращения.  
  
-   Указатель определяет адрес, выравнивание которого не подходит для типа указываемого объекта.  
  
-   Указатель определяет адрес, который не используется выполняемой программой.  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Оператор address-of: &](../cpp/address-of-operator-amp.md)   
 [Операторы косвенного обращения и адреса операнда](../c-language/indirection-and-address-of-operators.md)