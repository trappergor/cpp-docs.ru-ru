---
title: "Префикс операторы инкремента и декремента: ++ и--| Документы Microsoft"
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
- ++ operator [C++], prefix increment operators
- operators [C++], decrement
- -- operator [C++], prefix decrement operators [C++]
- operators [C++], increment
- decrement operators [C++], syntax
- decrement operators [C++]
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff153c462361e8b6bac8f3c10192025352da650f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="prefix-increment-and-decrement-operators--and---"></a>Префиксные операторы увеличения и уменьшения ++ и --
## <a name="syntax"></a>Синтаксис  
  
```  
++ unary-expression  
-- unary-expression  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор префиксного инкремента (`++`) добавляет единицу к своему операнду; это инкрементированное значение является результатом выражения. Операнд должен быть l значение типа, отличного от **const**. Результат — L-значение того же типа, как у операнда.  
  
 Оператор префиксного декремента (**--**) аналогичен оператору префиксного инкремента, за исключением того, что значение операнда уменьшается на единицу и результатом является это декрементированное значение.  

 **Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): операнд оператора инкремента или декремента не может иметь тип `bool`.
  
 Операторы префиксных и постфиксных инкремента и декремента влияют на свои операнды. Они различаются между собой порядком выполнения инкремента или декремента при вычислении выражения (Дополнительные сведения см. в разделе [постфиксных инкремента и декремента](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md).) В префиксной форме инкремент или декремент выполняется до использования значения при вычислении выражения, поэтому значение выражения отличается от значение операнда. В постфиксной форме инкремент или декремент выполняется после использования значения при вычислении выражения, поэтому значение выражения совпадает со значением операнда. Например, в следующей программе выполняется вывод на печать "`++i = 6`".  
  
```  
// expre_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int i = 5;  
   cout << "++i = " << ++i << endl;  
}  
```  
  
 Операнд целочисленного типа или типа с плавающей запятой инкрементируется или декрементируется на целое значение 1. Тип результата совпадает с типом операнда. Операнд типа указателя инкрементируется или декрементируется на значение размера объекта, к которому он относится. Инкрементированный указатель указывает на следующий объект, а декрементированный — на предыдущий.  
  
 Поскольку операторы инкремента и декремента имеют побочные эффекты, использование выражений с помощью операторов инкремента или декремента в [макрос препроцессора](../preprocessor/macros-c-cpp.md) может быть получен нежелательный результат. Рассмотрим следующий пример.  
  
```  
// expre_Increment_and_Decrement_Operators2.cpp  
#define max(a,b) ((a)<(b))?(b):(a)  
  
int main()  
{  
   int i = 0, j = 0, k;  
   k = max( ++i, j );  
}  
```  
  
 Макрос разворачивается до следующего выражения:  
  
```  
k = ((++i)<(j))?(j):(++i);  
```  
  
 Если значение `i` больше или равно `j` или меньше `j` на 1, оно будет инкрементировано дважды.  
  
> [!NOTE]
>  Встраиваемые функции C++ предпочтительнее макросов во многих случаях, поскольку исключают побочные эффекты, подобные описанным здесь, и позволяют языку выполнять более полную проверку типов.  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Префиксные операторы увеличения и уменьшения](../c-language/prefix-increment-and-decrement-operators.md)