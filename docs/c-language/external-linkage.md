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
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: c4a1981d2dd22f9ed8928b1d1daf71612b057e71
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="external-linkage"></a>Внешняя компоновка
Если в первом объявлении на уровне области видимости файла для идентификатора не используется описатель класса хранения **static**, объект имеет внешнюю компоновку.  
  
 Если в объявлении идентификатора для функции отсутствует описатель *storage-class-specifier*, его компоновка определяется так же, как если бы он был объявлен с описателем *storage-class-specifier* `extern`. Если объявление идентификатора объекта содержит область видимости файла и не содержит описатель *storage-class-specifier*, его компоновка является внешней.  
  
 Имя идентификатора с внешней компоновкой обозначает ту же функцию или объект данных, что и любое другое объявление того же имени с внешней компоновкой. Два объявления могут находиться в одной записи преобразования или в разных записях преобразования. Если объект или функция также имеет глобальное время жизни, объект или функция используется совместно всей программой.  
  
## <a name="see-also"></a>См. также  
 [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)
