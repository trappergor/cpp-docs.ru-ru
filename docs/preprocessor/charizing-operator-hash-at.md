---
title: "Оператор преобразования в символы (#@) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6521322e7a71d8e76b657fb8580157c036e881b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="charizing-operator-"></a>Оператор преобразования в символы (#@)
**Блок, относящийся только к системам Microsoft**  
  
 Оператор образования символа может использоваться только в аргументах макросов. Если  **#@**  перед формальным параметром в определении макроса, фактический аргумент заключено в одинарные кавычки и при разворачивании макроса обрабатывается как символ. Пример:  
  
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