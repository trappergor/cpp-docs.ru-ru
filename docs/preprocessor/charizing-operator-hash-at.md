---
title: Оператор преобразования в символы (#@) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9e0c0d140d937b7359ff3abf9c0eae145a89210
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="charizing-operator-"></a>Оператор преобразования в символы (#@)
**Блок, относящийся только к системам Microsoft**  
  
 Оператор образования символа может использоваться только в аргументах макросов. Если **#@** перед формальным параметром в определении макроса, фактический аргумент заключено в одинарные кавычки и при разворачивании макроса обрабатывается как символ. Пример:  
  
```  
#define makechar(x)  #@x  
```  
  
 приводит к разворачиванию оператора  
  
```  
a = makechar(b);  
```  
  
 в выражение  
  
```  
a = 'b';  
```  
  
 В операторе образования символа не допускается использовать одинарные кавычки.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Операторы препроцессора](../preprocessor/preprocessor-operators.md)