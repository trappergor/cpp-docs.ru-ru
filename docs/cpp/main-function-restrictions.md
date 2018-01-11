---
title: "Ограничения функции Main | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Main
dev_langs: C++
helpviewer_keywords: main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a94844a0d5636c58a764114ed6f413923d69950
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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