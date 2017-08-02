---
title: "Строковые литералы в C | Документация Майкрософт"
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
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 2ca39273bff41d1a08d078445ddf8d8b56252db8
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="c-string-literals"></a>Строковые литералы в C
"Строковый литерал" — это последовательность символов исходной кодировки, заключенных в двойные кавычки (**" "**). Строковые литералы используются для представления последовательности символов, которые вместе образуют строку, завершающуюся нуль-символом. Перед двухбайтовыми строковыми литералами всегда должна ставиться буква **L**.  
  
## <a name="syntax"></a>Синтаксис  
 *string-literal*:  
 **"** *s-char-sequence* opt**"**  
  
 **L"** *s-char-sequence* opt**"**  
  
 *s-char-sequence*:  
 *s-char*  
  
 *s-char-sequence s-char*  
  
 *s-char*:  
 любой член исходной кодировки, кроме двойной кавычки ("), обратной косой черты (\\) и символа новой строки  
  
 *escape-sequence*  
  
 В приведенном ниже примере показан простой строковый литерал.  
  
```  
char *amessage = "This is a string literal.";  
```  
  
 В строковых литералах допустимо использовать все коды, перечисленные в [таблице escape-последовательностей](../c-language/escape-sequences.md). Для представления в строковом литерале двойной кавычки следует использовать escape-последовательность **\\"**. Одинарная кавычка (**'**) может быть представлена без escape-последовательности. Если в строке имеется обратная косая черта (**\\**), после нее должна следовать вторая такая черта (**\\\\**). Если обратная косая черта находится в конце строки, она всегда интерпретируется как символ объединения строк.  
  
## <a name="see-also"></a>См. также  
 [Элементы языка C](../c-language/elements-of-c.md)
