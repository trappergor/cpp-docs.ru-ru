---
title: Строковые литералы в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 303ad83c5e366f32a99a501a58b168ef25adbb42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382787"
---
# <a name="c-string-literals"></a>Строковые литералы в C
"Строковый литерал" — это последовательность символов исходной кодировки, заключенных в двойные кавычки (**" "**). Строковые литералы используются для представления последовательности символов, которые вместе образуют строку, завершающуюся нуль-символом. Перед двухбайтовыми строковыми литералами всегда должна ставиться буква **L**.  
  
## <a name="syntax"></a>Синтаксис  
 *string-literal*:  
 **"** *s-char-sequence* opt **"**  
  
 **L"** *s-char-sequence* opt **"**  
  
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