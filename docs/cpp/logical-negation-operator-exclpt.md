---
title: 'Оператор логического отрицания: ! | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b64e9887e51666405d3c6c106b40c99528ea4510
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="logical-negation-operator-"></a>Оператор логического отрицания: !
## <a name="syntax"></a>Синтаксис  
  
```  
  
! cast-expression  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор логического отрицания (**!**) меняет значение своего операнда на противоположное. Операнд должен иметь арифметический тип или тип указателя (либо выражение, результатом которого является арифметический тип или тип указателя). Операнд неявно преобразуется в тип `bool`. В результате **true** Если преобразованный операнд — **false**; в результате **false** Если преобразованный операнд — **true**. Результат имеет тип `bool`.  
  
 Для выражения *e*, унарное выражение **! *** e* эквивалентно выражению **(*** e* `==` 0), за исключением случаев, когда используются перегруженные операторы.  
  
## <a name="operator-keyword-for-"></a>Ключевое слово оператора для !  
 **Не** оператор является текстовым эквивалентом **!**. Существует два способа доступа к **не** оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)