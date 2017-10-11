---
title: "Оператор NULL в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 4ead6c1bb4ad5330ed23c90019ec4e5e03282fb8
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
