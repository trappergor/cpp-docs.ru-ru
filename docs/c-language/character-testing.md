---
title: Тестирование символов | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdf65de941486cb8256ba8e30a3f186d3e3702d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="character-testing"></a>Тестирование символов
**ANSI 4.3.1** Наборы символов, тестируемые функциями `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` и `isupper`  
  
 В следующей таблице приведено описание этих функций в соответствии с реализацией компилятором Microsoft C.  
  
|Функция|Тестируемые наборы символов|  
|--------------|---------------|  
|`isalnum`|Символы 0–9, A–Z, a–z (коды ASCII 48–57, 65–90, 97–122)|  
|`isalpha`|Символы A–Z, a–z (коды ASCII 65–90, 97–122)|  
|`iscntrl`|Коды ASCII 0–31, 127|  
|`islower`|Символы a–z (коды ASCII 97–122)|  
|`isprint`|Символы A–Z, a–z, 0–9, пунктуация, пробел (коды ASCII 32–126)|  
|`isupper`|Символы A–Z (коды ASCII 65–90)|  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)