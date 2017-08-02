---
title: "Юникод. Набор расширенных символов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
caps.latest.revision: 8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 29991216bd5ee6cb76908ef408cc56240a726e26
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="unicode-the-wide-character-set"></a>Юникод. Набор расширенных символов
Расширенный символ — это двухбайтовый многоязыковой код символа. Все символы, используемые в современных вычислительных системах по всему миру, включая технические символы и специальные знаки, используемые в издательском деле, могут быть представлены в соответствии со стандартом Юникода в виде расширенных символов. Разработанный и поддерживаемый большим консорциумом, который включает Microsoft, стандарт Юникода теперь является общепринятым.  
  
 Расширенный символ типа `wchar_t`. Строка расширенных символов представляется как массив `wchar_t[]`, и на нее указывает указатель `wchar_t*`. Любой символ ASCII может быть представлен как расширенный символ путем добавления к нему префикса `L`. Например, "L'\0'" является 16-разрядным конечным знаком Юникода для значения `NULL`. Подобным образом все строковые литералы, составленные из знаков ASCII, могут быть представлены как строковые литералы в формате Юникода с помощью простого добавления к литералу ASCII префикса "L" (L"Hello").  
  
 Как правило, расширенные символы занимают больший объем памяти, чем многобайтовые знаки, однако обрабатываются они быстрее. Кроме того, при многобайтовом кодировании одновременно может быть представлен только один языковой стандарт, в то время как в Юникоде одновременно могут быть представлены все мировые кодировки.  
  
## <a name="see-also"></a>См. также  
 [Интернационализация](../c-runtime-library/internationalization.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
