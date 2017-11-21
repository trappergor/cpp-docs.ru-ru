---
title: "Оператор Return (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: return_cpp
dev_langs: C++
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db65a7762659bfc71f7ef33dc9f8b9b732fda091
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="return-statement-c"></a>Оператор return (C++)
Завершает выполнение функции и возвращает элемент управления в вызывающую функцию (или в операционную систему при передаче управления из функции `main`). Выполнение возобновляется в вызывающей функции в точке сразу после вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
return [expression];  
```  
  
## <a name="remarks"></a>Примечания  
 Предложение `expression`, при его наличии, преобразуется в тип, указанный в объявлении функции, как если бы выполнялась инициализация. В результате преобразования из типа выражения в тип `return` функции могут быть созданы временные объекты. Дополнительные сведения о том, как и когда временные объекты создаются в разделе [временные объекты](../cpp/temporary-objects.md).  
  
 Значение предложения `expression` возвращается в вызывающую функцию. Если выражение пропущено, то возвращаемое значение функции не определено. Конструкторы и деструкторы и функции типа `void`, нельзя указать выражение в `return` инструкции. Функции всех других типов должны указать выражение в операторе `return`.  
  
 Если поток элемента управления выходит из блока, включающего определение функции, результат будет таким же, как если бы был выполнен оператор `return` без выражения. Это недопустимо для функций, объявленных как возвращающие значение.  
  
 Функция может иметь неограниченное число операторов `return`.  
  
 В следующем примере используется выражение с оператором `return` для получения наибольшего из двух целых чисел.  
  
## <a name="example"></a>Пример  
  
```  
// return_statement2.cpp  
#include <stdio.h>  
  
int max ( int a, int b )  
{  
   return ( a > b ? a : b );  
}  
  
int main()  
{  
    int nOne = 5;  
    int nTwo = 7;  
  
    printf_s("\n%d is bigger\n", max( nOne, nTwo ));  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы перехода](../cpp/jump-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)