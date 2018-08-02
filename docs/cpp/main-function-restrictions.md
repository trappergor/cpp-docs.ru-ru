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
ms.openlocfilehash: 981d4c8c0ef30993811e5dbb6fd0a112a6447011
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406498"
---
# <a name="main-function-restrictions"></a>Ограничения функции main
Несколько ограничений **основной** функцию, которая не применяются для любых других функций C++. **Основной** функции:  
  
-   Не может быть перегружен (см. в разделе [перегрузка функций](function-overloading.md)).  
  
-   Не могут объявляться как **встроенного**.  
  
-   Не могут объявляться как **статических**.  
  
-   Нельзя получить ее адрес.  
  
-   Вызвать невозможно.  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)