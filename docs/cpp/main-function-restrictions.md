---
title: Ограничения функции Main | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed5be2df6e152b26bcade1970b35ad33655e8e02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419689"
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