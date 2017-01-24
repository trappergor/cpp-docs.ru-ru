---
title: "Проверка символов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Проверка символов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.3.1** Наборы символов, тестируемые функциями `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` и `isupper`  
  
 В следующей таблице приведено описание этих функций в соответствии с реализацией компилятором Microsoft C.  
  
|Функция|Тестируемые наборы символов|  
|-------------|---------------------------------|  
|`isalnum`|Символы 0\-9, A\-Z, a\-z \(коды ASCII 48\-57, 65\-90, 97\-122\)|  
|`isalpha`|Символы A\-Z, a\-z \(коды ASCII 65\-90, 97\-122\)|  
|`iscntrl`|Коды ASCII 0\-31, 127|  
|`islower`|Символы a\-z \(коды ASCII 97\-122\)|  
|`isprint`|Символы A\-Z, a\-z, 0\-9, пунктуация, пробел \(коды ASCII 32\-126\)|  
|`isupper`|Символы A\-Z \(коды ASCII 65\-90\)|  
  
## См. также  
 [Функции библиотеки](../c-language/library-functions.md)