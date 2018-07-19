---
title: Оператор NULL в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72e120fa412481a8313809bd5cdaf748de498bde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384272"
---
# <a name="null-statement-c"></a>Оператор NULL (C)
Оператор null — это оператор, содержащий только точку с запятой. Он может отображаться в любом месте, где ожидается оператор. При выполнении оператора null ничего не происходит. Ниже описан правильный способ кодирования оператора null.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Некоторые операторы, например **do**, **for**, **if** и `while`, требуют, чтобы исполняемые операторы были представлены в теле оператора. Оператор null соответствует синтаксическим требованиям в случаях, когда существенная основная часть оператора не требуется.  
  
 Как и с любым другим оператором С, можно включить метку перед оператором null. Чтобы пометить элемент, не являющийся оператором, например закрывающую скобку составного оператора, можно пометить оператор null и включить его сразу перед элементом. Результат будет тем же самым.  
  
 В следующем примере показан оператор null.  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 Здесь выражение цикла `line[i++] = 0` в операторе **for** инициализирует первые 10 элементов массива `line` значением 0. Основная часть оператора представляет собой оператор null, поскольку остальные операторы не требуются.  
  
## <a name="see-also"></a>См. также  
 [Операторы](../c-language/statements-c.md)