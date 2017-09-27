---
title: "Компоновка в именах в области видимости класса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
ms.openlocfilehash: 37a0dcca1da0ae56a8144adf862eda89bfb1c4d6
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-class-scope"></a>Компоновка в именах в области класса
Для имен с областью видимости класса применяются следующие правила компоновки:  
  
-   статические члены класса имеют внешнюю компоновку;  
  
-   функции-члены класса имеют внешнюю компоновку;  
  
-   перечислители и имена `typedef` не имеют компоновки.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
-   Функции, объявленные как функции `friend`, должны иметь внешнюю компоновку. Объявление статической функции как функции `friend` приводит к ошибке.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Программа и компоновка](../cpp/program-and-linkage-cpp.md)
