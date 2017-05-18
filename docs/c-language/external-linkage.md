---
title: "Внешняя компоновка | Документация Майкрософт"
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
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
caps.latest.revision: 6
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: dcd269984d3b56728a5a135a380aacb7efae8c98
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="external-linkage"></a>Внешняя компоновка
Если в первом объявлении на уровне области видимости файла для идентификатора не используется описатель класса хранения **static**, объект имеет внешнюю компоновку.  
  
 Если в объявлении идентификатора для функции отсутствует описатель *storage-class-specifier*, его компоновка определяется так же, как если бы он был объявлен с описателем *storage-class-specifier* `extern`. Если объявление идентификатора объекта содержит область видимости файла и не содержит описатель *storage-class-specifier*, его компоновка является внешней.  
  
 Имя идентификатора с внешней компоновкой обозначает ту же функцию или объект данных, что и любое другое объявление того же имени с внешней компоновкой. Два объявления могут находиться в одной записи преобразования или в разных записях преобразования. Если объект или функция также имеет глобальное время жизни, объект или функция используется совместно всей программой.  
  
## <a name="see-also"></a>См. также  
 [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)
