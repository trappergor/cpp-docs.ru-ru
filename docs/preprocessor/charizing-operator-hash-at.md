---
title: "Оператор преобразования в символы (#@) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#@'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 933e97732462b61919d9e5a1e73f2a72d26ea01b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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