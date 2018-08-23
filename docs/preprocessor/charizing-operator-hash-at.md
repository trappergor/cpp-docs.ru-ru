---
title: Оператор преобразования в символы (#@) | Документация Майкрософт
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
ms.openlocfilehash: c6aa18936497f0415da331697aceb26f26345500
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540069"
---
# <a name="charizing-operator-"></a>Оператор преобразования в символы (#@)
**Блок, относящийся только к системам Microsoft**  
  
Оператор образования символа может использоваться только в аргументах макросов. Если `#@` стоит перед формальным параметром в определении макроса, фактический аргумент заключены в одинарные кавычки и рассматривается как символ, при разворачивании макроса. Пример:  
  
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