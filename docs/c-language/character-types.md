---
title: Символьные типы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd26eea35da463211b144e98faa0636f5204f6f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383697"
---
# <a name="character-types"></a>Символьные типы
Целочисленная символьная константа, в начале которой не указана буква **L**, имеет тип `int`. Значением целой символьной константы, содержащей один символ, является численное значение символа, интерпретированное как целое число. Например, численное значение символа `a` равно 97 в десятичном представлении и 61 в шестнадцатеричном представлении.  
  
 Синтаксически "расширенная символьная константа" представляет собой символьную константу с префиксом в виде буквы **L**. Расширенная символьная константа имеет тип `wchar_t` — целочисленный тип, определенный в файле заголовка STDDEF.H. Пример:  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Расширенные символьные константы имеют ширину 16 бит и указывают члены расширенной кодировки выполнения. Они обеспечивают представление символов в алфавитах, слишком больших для представления типом `char`. Дополнительные сведения о расширенных символах см. в статье [Многобайтовые и расширенные символы](../c-language/multibyte-and-wide-characters.md).  
  
## <a name="see-also"></a>См. также  
 [Константы символов в C](../c-language/c-character-constants.md)