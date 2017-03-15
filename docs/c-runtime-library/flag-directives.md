---
title: "Директивы флагов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- format specification fields for printf function
- print flag directives
- printf function, format specification fields
- flag directives printf function
ms.assetid: b00cbdc9-1e5c-4b30-9f56-c1ef8d383767
caps.latest.revision: 12
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
ms.openlocfilehash: 36f7db99d3fc9bb5346ae5f1dc96b846ae964714
ms.lasthandoff: 02/24/2017

---
# <a name="flag-directives"></a>Директивы флагов
В спецификации формата первым необязательным полем является `flags`. Директива флагов — это символ, задающий правила выравнивания и вывода знаков, пробелов, ведущих нулей, десятичных запятых, восьмеричных и шестнадцатеричных префиксов. В спецификации формата может быть указано несколько директив флагов, и флаги могут размещаться в любом порядке.  
  
### <a name="flag-characters"></a>Символы флагов  
  
|Flag|Значение|Default|  
|----------|-------------|-------------|  
|`–`|Выравнивание результата по левому краю в пределах заданной ширины поля.|Выравнивание по правому краю.|  
|`+`|Если выходное значение имеет тип со знаком, используйте для него префикс + или –.|Знак отображается только для отрицательных значений со знаком –.|  
|`0`|Если `width` предшествует префикс `0`, добавляется несколько ведущих нулей для достижения минимальной ширины. Если указаны одновременно `0` и `–`, знак `0` игнорируется. Если `0` указывается в целочисленном формате (`i`, `u`, `x`, `X`, `o`, `d`) и в сочетании со спецификацией точности, (например, `%04.d`), знак `0` игнорируется.|Без заполнения.|  
|пустой (' ')|Используйте пустой префикс для положительных выходных значений со знаком. Пустой префикс игнорируется, если одновременно с ним присутствует флаг +.|Пустой префикс не отображается.|  
|`#`|Если используется в сочетании с форматом `o`, `x` или `X`, флаг `#` выводит префикс 0, 0x или 0X соответственно для всех ненулевых выходных значений.|Пустой префикс не отображается.|  
||Если используется в сочетании с форматом `e`, `E`, `f`, `a` или `A`, флаг `#` принудительно добавляет десятичный разделитель к выходному значению.|Десятичный разделитель появляется, только если после него есть цифры.|  
||Если используется в сочетании с форматом `g` или `G`, флаг `#` принудительно добавляет десятичный разделитель к выходному значению и запрещает отбрасывать конечные нули.<br /><br /> Флаг игнорируется в сочетании с форматами `c`, `d`, `i`, `u` и `s`.|Десятичный разделитель появляется, только если после него есть цифры. Конечные нули отбрасываются.|  
  
## <a name="see-also"></a>См. также  
 [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Синтаксис описания формата: функции printf и wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Спецификация ширины printf](../c-runtime-library/printf-width-specification.md)   
 [Спецификация точности](../c-runtime-library/precision-specification.md)   
 [Спецификация размера](../c-runtime-library/size-specification.md)   
 [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md)
