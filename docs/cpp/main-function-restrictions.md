---
title: "Ограничения функции Main | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 10fe82b0bb7ad700164b05ba466854db7716ba76
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="main-function-restrictions"></a>Ограничения функции main
Несколько ограничений **основной** функции, которые не применяются к каким другим функциям C++. **Основной** функции:  
  
-   Не может быть перегружен (см. [перегрузка функций](function-overloading.md)).  
  
-   Не могут объявляться как **встроенного**.  
  
-   Не могут объявляться как **статических**.  
  
-   Нельзя получить ее адрес.  
  
-   Вызвать невозможно.  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)
