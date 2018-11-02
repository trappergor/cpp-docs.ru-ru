---
title: Базовые классы
ms.date: 11/04/2016
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
ms.openlocfilehash: faae9ba8591f296a48665e481678e2808aae7662
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628312"
---
# <a name="base-classes"></a>Базовые классы

Процесс наследования создает новый производный класс, который состоит из членов базового класса или классов и всех новых элементов, добавленных производным классом. В множественном наследовании можно создать граф наследования, где один и тот же базовый класс является частью нескольких производных классов. На следующем рисунке показан такой граф.

![Несколько экземпляров базового класса](../cpp/media/vc38xn1.gif "vc38XN1") несколько экземпляров одного базового класса

На рисунке представлены наглядные представления компонентов `CollectibleString` и `CollectibleSortable`. Однако базовый класс (`Collectible`) находится в `CollectibleSortableString` на протяжении путей `CollectibleString` и `CollectibleSortable`. Для устранения этой избыточности такие классы при наследовании можно объявлять как виртуальные базовые классы.