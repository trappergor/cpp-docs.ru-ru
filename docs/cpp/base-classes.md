---
title: Базовые классы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a6d6494cc1ef371cfeb51647bc310a74ac68bfb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059216"
---
# <a name="base-classes"></a>Базовые классы

Процесс наследования создает новый производный класс, который состоит из членов базового класса или классов и всех новых элементов, добавленных производным классом. В множественном наследовании можно создать граф наследования, где один и тот же базовый класс является частью нескольких производных классов. На следующем рисунке показан такой граф.

![Несколько экземпляров базового класса](../cpp/media/vc38xn1.gif "vc38XN1") несколько экземпляров одного базового класса

На рисунке представлены наглядные представления компонентов `CollectibleString` и `CollectibleSortable`. Однако базовый класс (`Collectible`) находится в `CollectibleSortableString` на протяжении путей `CollectibleString` и `CollectibleSortable`. Для устранения этой избыточности такие классы при наследовании можно объявлять как виртуальные базовые классы.