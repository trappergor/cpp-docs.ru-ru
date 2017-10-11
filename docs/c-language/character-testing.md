---
title: "Тестирование символов | Документы Майкрософт"
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
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 89f48346d9b96c7de20c11fd4cbcde106571ed57
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
