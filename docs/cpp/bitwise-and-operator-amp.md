---
title: "Оператор побитового и: &amp; | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitand
dev_langs:
- C++
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 99ff65f38abf5cfcac135e2cc54e3df6df5f336d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="bitwise-and-operator-amp"></a>Оператор побитового и:&amp;
## <a name="syntax"></a>Синтаксис  
  
```  
  
expression   
&  
 expression  
  
```  
  
## <a name="remarks"></a>Примечания  
 Выражения могут представлять собой другие and-выражения или (в зависимости от упомянутых ниже типов ограничений) выражения равенства, выражения связей, выражения сложения, выражения умножения, выражения указателя на член, выражения приведения, унарные выражения, постфиксные выражения или основные выражения.  
  
 Побитовый оператор AND (**&**) сравнивает каждый бит первого операнда с соответствующим битом второго операнда. Если оба бита равны 1, соответствующий бит результата устанавливается равным единице. в противном случае — нулю.  
  
 Оба операнда оператора побитового И должны иметь целочисленный тип. Обычные арифметические преобразования, описанные в [стандартные преобразования](standard-conversions.md), применяются к операндам.  
  
## <a name="operator-keyword-for-"></a>Ключевое слово оператора &  
 `bitand` Оператор является текстовым эквивалентом ** & **. Существует два способа доступа к `bitand` оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Встроенные операторы C++, приоритет и ассоциативность](cpp-built-in-operators-precedence-and-associativity.md)  
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Побитовые операторы в C](../c-language/c-bitwise-operators.md)
