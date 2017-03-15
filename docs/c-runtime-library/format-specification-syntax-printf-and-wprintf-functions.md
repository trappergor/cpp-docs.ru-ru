---
title: "Синтаксис описания формата: функции printf и wprintf | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- wprintf
dev_langs:
- C++
helpviewer_keywords:
- format specification fields for printf function
- print flag directives
- printf function, precision
- type fields, printf function
- precision fields
- printf function, format specification fields
- flag directives printf function
- type fields
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
caps.latest.revision: 15
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1843e4f826606f85aa96d1faf65e4af3f80769ea
ms.lasthandoff: 02/24/2017

---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>Синтаксис описания формата: функции printf и wprintf
Описывает синтаксис для аргументов строки форматирования в `printf`, `wprintf` и связанных с ними функциях. Существуют более безопасные версии этих возможностей. Дополнительные сведения см. в статье [Функции безопасности в CRT](../c-runtime-library/security-features-in-the-crt.md). Дополнительные сведения об отдельных функциях см. в документации по конкретным функциям. Список этих функций см. в разделе [Потоковый ввод-вывод](../c-runtime-library/stream-i-o.md).  
  
 Спецификация формата, состоящая из дополнительных и обязательных полей, имеет следующую форму:  
  
 `%`[[flags](../c-runtime-library/flag-directives.md)] [[width](../c-runtime-library/printf-width-specification.md)] [**.**[precision](../c-runtime-library/precision-specification.md)] [{`h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`}] [type](../c-runtime-library/printf-type-field-characters.md)  
  
 Каждое поле спецификации формата — это символ или число, указывающее конкретный параметр формата или описатель преобразования. Обязательный символ `type` определяет тип преобразования, которое применяется к аргументу. Необязательные поля `flags`, `width` и `precision` управляют дополнительными аспектами формата. Базовая спецификация формата содержит только символ процента и символ `type` — например, `%s`, что определяет преобразование строк. Если в безопасных версиях функций за символом процента следует символ, который не имеет смысла в поле формата, вызывается обработчик недопустимого параметра. Дополнительные сведения см. в разделе [Проверка параметров](../c-runtime-library/parameter-validation.md). В небезопасных версиях символ копируется в выходные данные без изменений. Чтобы вывести символ знака процента, используйте `%%`.  
  
 Поля спецификации формата управляют следующими аспектами преобразования и форматирования аргумента:  
  
 `type`  
 Обязательный символ описателя преобразования, который определяет, интерпретируется ли связанный `argument` как символ, строка, целое число или число с плавающей запятой. Дополнительные сведения см. в статье [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md).  
  
 `flags`  
 Дополнительный символ или символы, управляющие выравниванием выходных данных и выводом знаков, пробелов, ведущих нулей, десятичных запятых и восьмеричных и шестнадцатеричных префиксов. Дополнительные сведения см. в статье [Директивы флагов](../c-runtime-library/flag-directives.md). В спецификации формата может быть указано несколько флагов, и флаги могут размещаться в любом порядке.  
  
 `width`  
 Необязательное десятичное число, указывающее минимальное количество выводимых символов. Дополнительные сведения см. в статье [Спецификация ширины printf](../c-runtime-library/printf-width-specification.md).  
  
 `precision`  
 Необязательное десятичное число, указывающее максимальное количество символов, выводимых для строк, количество значащих цифр или число цифр после десятичной запятой для значений с плавающей запятой либо минимальное число цифр, выводимых для целых значений. Дополнительные сведения см. в таблице "Как значение точности влияет на тип" статьи [Спецификация точности](../c-runtime-library/precision-specification.md).  
  
 `h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`  
 Необязательные префиксы в `type`, определяющие размер соответствующего аргумента. Дополнительные сведения см. в таблице с префиксами размера статьи [Спецификация размера](../c-runtime-library/size-specification.md).  
  
> [!IMPORTANT]
>  Убедитесь, что строки спецификации формата не определяются пользователем. Например, рассмотрим программу, которая предлагает пользователю ввести имя и сохраняет введенные данные в строковой переменной с именем `name`. Для печати переменной `name` не используйте следующий код:  
>   
>  `printf( name ); /* Danger!  If name contains "%s", program will crash */`  
>   
>  Вместо этого используйте следующий код:  
>   
>  `printf( "%s", name );`  
  
## <a name="see-also"></a>См. также  
 [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [Позиционные параметры printf_p](../c-runtime-library/printf-p-positional-parameters.md)   
 [Директивы флагов](../c-runtime-library/flag-directives.md)   
 [Спецификация ширины printf](../c-runtime-library/printf-width-specification.md)   
 [Спецификация точности](../c-runtime-library/precision-specification.md)   
 [Спецификация размера](../c-runtime-library/size-specification.md)   
 [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md)
