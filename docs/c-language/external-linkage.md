---
title: Внешняя компоновка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be268dbc153ad0bb140a2adfcfd8ec6385716c48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027567"
---
# <a name="external-linkage"></a>Внешняя компоновка

Если в первом объявлении на уровне области видимости файла для идентификатора не используется описатель класса хранения **static**, объект имеет внешнюю компоновку.

Если в объявлении идентификатора для функции отсутствует описатель *storage-class-specifier*, его компоновка определяется так же, как если бы он был объявлен с описателем *storage-class-specifier* `extern`. Если объявление идентификатора объекта содержит область видимости файла и не содержит описатель *storage-class-specifier*, его компоновка является внешней.

Имя идентификатора с внешней компоновкой обозначает ту же функцию или объект данных, что и любое другое объявление того же имени с внешней компоновкой. Два объявления могут находиться в одной записи преобразования или в разных записях преобразования. Если объект или функция также имеет глобальное время жизни, объект или функция используется совместно всей программой.

## <a name="see-also"></a>См. также

[Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)