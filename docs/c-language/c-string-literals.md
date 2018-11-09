---
title: Строковые литералы в C
ms.date: 08/31/2018
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
ms.openlocfilehash: bd8b49645e34224cbea7e801f197bfbcbc012915
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635630"
---
# <a name="c-string-literals"></a>Строковые литералы в C

"Строковый литерал" — это последовательность символов исходной кодировки, заключенных в двойные кавычки (**" "**). Строковые литералы используются для представления последовательности символов, которые вместе образуют строку, завершающуюся нуль-символом. Перед двухбайтовыми строковыми литералами всегда должна ставиться буква **L**.

## <a name="syntax"></a>Синтаксис

*string-literal*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**"** *s-char-sequence*<sub>opt</sub> **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**L"** *s-char-sequence*<sub>opt</sub> **"**

*s-char-sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*s-char*

&nbsp;&nbsp;&nbsp;&nbsp;*s-char-sequence* *s-char*

*s-char*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;любой член исходной кодировки, кроме двойной кавычки ("), обратной косой черты (\\) и символа новой строки<br/>

&nbsp;&nbsp;&nbsp;&nbsp;*escape-sequence*

## <a name="remarks"></a>Примечания

В приведенном ниже примере показан простой строковый литерал.

```C
char *amessage = "This is a string literal.";
```

В строковых литералах допустимо использовать все коды, перечисленные в [таблице escape-последовательностей](../c-language/escape-sequences.md). Для представления в строковом литерале двойной кавычки следует использовать escape-последовательность **\\"**. Одинарная кавычка (**'**) может быть представлена без escape-последовательности. Если в строке имеется обратная косая черта (**\\**), после нее должна следовать вторая такая черта (**\\\\**). Если обратная косая черта находится в конце строки, она всегда интерпретируется как символ объединения строк.

## <a name="see-also"></a>См. также

[Элементы языка C](../c-language/elements-of-c.md)
