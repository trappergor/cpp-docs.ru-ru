---
title: Компоновка в именах в области видимости класса | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- classes [C++], scope
- external linkage, scope linkage rules
- class names [C++], linkage
- classes [C++], names
- scope [C++], class names
- class scope [C++], linkage in names with
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9eb58f87e998fbe1eeeb9b26eb0da75046a9079d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="linkage-in-names-with-class-scope"></a>Компоновка в именах в области класса
Для имен с областью видимости класса применяются следующие правила компоновки:  
  
-   статические члены класса имеют внешнюю компоновку;  
  
-   функции-члены класса имеют внешнюю компоновку;  
  
-   перечислители и имена `typedef` не имеют компоновки.  
  
 **Блок, относящийся только к системам Microsoft**  
  
-   Функции, объявленные как функции `friend`, должны иметь внешнюю компоновку. Объявление статической функции как функции `friend` приводит к ошибке.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Программа и компоновка](../cpp/program-and-linkage-cpp.md)