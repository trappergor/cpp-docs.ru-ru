---
title: "Многобайтовая кодировка и расширенные символы | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- character data types [C]
- Unicode [C++], wide character set
- types [C], character
- characters [C++], wide
- international applications [C++], character display
- multibyte characters [C++]
- wide characters [C++]
- characters [C++], codes
- character codes [C++], wide
- character codes [C++], multibyte
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
caps.latest.revision: 6
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9087cf4e510d4355af1164d5a46d0afaee9ae8ab
ms.lasthandoff: 02/24/2017

---
# <a name="multibyte-and-wide-characters"></a>Многобайтовая кодировка и расширенные символы
Многобайтовые символы — это символы, составленные последовательностями из одного или нескольких байтов. Каждая последовательность байтов представляет отдельный символ в расширенном наборе символов. Многобайтовые символы используются в таких кодировках, как Кандзи.  
  
 Расширенные символы — это коды многоязычных символов, которые всегда имеют размер 16 бит. Символьные константы имеют тип `char`; для расширенных символов используется тип `wchar_t`. Поскольку расширенные символы всегда имеют фиксированный размер, их использование упрощает программирование с использованием международных кодировок.  
  
 Строковый литерал с расширенными символами `L"hello"` становится массивом из шести целочисленных значений типа `wchar_t`.  
  
```  
{L'h', L'e', L'l', L'l', L'o', 0}  
```  
  
 Расширенные символы определены в спецификации Юникода. Преобразование между многобайтовыми и расширенными символами выполняется процедурами библиотеки времени выполнения `mbstowcs`, `mbtowc`, `wcstombs` и `wctomb`.  
  
## <a name="see-also"></a>См. также  
 [Идентификаторы C](../c-language/c-identifiers.md)
