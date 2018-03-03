---
title: "Регистратор ATL и форма Бэкуса Nauer форма синтаксиса (BNF) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01d364313420c0a950f8eba222e3ae020fbd86cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>Основные сведения о синтаксис Nauer Бэкуса формы (BNF)
В этом разделе, с помощью синтаксиса BNF, который использует нотацию, показанные в следующей таблице описаны сценарии, используемые регистратором ATL.  
  
|Соглашение о символ|Значение|  
|------------------------|-------------|  
|`::=`|Эквивалент|  
|`&#124;`|OR|  
|`X+`|Один или несколько `X`s.|  
|`[X]`|Параметр `X` является необязательным. Необязательные разделители обозначены `[]`.|  
|Любой **полужирным** текста|Строковый литерал.|  
|Любой *выделены курсивом* текста|Как создать строковый литерал.|  
  
 Как показано в предыдущей таблице, строковые литералы используются скрипты регистратора. Эти значения являются фактический текст, который должен находиться в сценарии. В следующей таблице описаны строковые литералы, использующиеся в скрипте ATL регистратора.  
  
|Строковый литерал|Действие|  
|--------------------|------------|  
|**ForceRemove**|Полностью удаляет следующий ключ (если он существует) и повторно создает ее.|  
|**NoRemove**|Не удаляйте следующий ключ во время отменить регистрацию.|  
|**функция Val**|Указывает, что `<Key Name>` является именованное значение.|  
|**Удалить**|Удаляет следующий ключ во время регистрации.|  
|**s**|Указывает, что следующее значение является строкой (**REG_SZ**).|  
|**d**|Указывает, что следующее значение **DWORD** (**REG_DWORD**).|  
|**m**|Указывает, что следующее значение multistring (**REG_MULTI_SZ**).|  
|**b**|Указывает, что следующее значение двоичное значение (**REG_BINARY**).|  
  
## <a name="bnf-syntax-examples"></a>Примеры синтаксиса BNF  
 Вот несколько примеров синтаксиса, помогут вам понять принципы работы нотации и строковые литералы в скрипте регистратор ATL.  
  
### <a name="syntax-example-1"></a>Пример синтаксиса 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 Указывает, что `registry expression` эквивалентно `Add Key`.  
  
### <a name="syntax-example-2"></a>Пример синтаксиса 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 Указывает, что `registry expression` эквивалентен типу `Add Key` или `Delete Key`.  
  
### <a name="syntax-example-3"></a>Пример синтаксиса 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 Указывает, что `Key Name` соответствует одному или нескольким `AlphaNumerics`.  
  
### <a name="syntax-example-4"></a>Пример синтаксиса 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 Указывает, что `Add Key` эквивалентно `Key Name`и что строковых литералов, `ForceRemove`, `NoRemove`, и `val`, являются необязательными.  
  
### <a name="syntax-example-5"></a>Пример синтаксиса 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 Указывает, что `AlphaNumeric` является эквивалентом для любой НЕНУЛЕВОЙ символ.  
  
### <a name="syntax-example-6"></a>Пример синтаксиса 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 Указывает, что имя ключа `testmulti` multistring значение состоит из `String 1` и `String 2`.  
  
### <a name="syntax-example-7"></a>Пример синтаксиса 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 Указывает, что имя ключа `testhex` — **DWORD** присвоено шестнадцатеричное 55 (десятичное 85). Обратите внимание, этот формат соответствует **& H** нотации, как найти в спецификации Visual Basic.  
  
## <a name="see-also"></a>См. также  
 [Создание скриптов регистратора](../atl/creating-registrar-scripts.md)

