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
ms.openlocfilehash: 1920d8183607140ebe38aaf56a447bc9cd3010f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="charizing-operator-"></a>Оператор преобразования в символы (#@)
**Блок, относящийся только к системам Майкрософт**  
  
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