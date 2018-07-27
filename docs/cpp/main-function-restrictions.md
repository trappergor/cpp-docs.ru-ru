---
title: Ограничения функции Main | Документация Майкрософт
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
ms.openlocfilehash: 3114f1ef379495f36f4231dbad6fd41ac145bcfe
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941750"
---
# <a name="main-function-restrictions"></a>Ограничения функции main
Несколько ограничений `main` функцию, которая не применяются для любых других функций C++. `main` Функции:  
  
-   Не может быть перегружен (см. в разделе [перегрузка функций](function-overloading.md)).  
  
-   Не могут объявляться как **встроенного**.  
  
-   Не могут объявляться как **статических**.  
  
-   Нельзя получить ее адрес.  
  
-   Вызвать невозможно.  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)