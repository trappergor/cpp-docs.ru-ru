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
ms.openlocfilehash: f1375cee34266b8d751e9c8d88fb22ce56f6c044
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407992"
---
# <a name="base-classes"></a>Базовые классы
Процесс наследования создает новый производный класс, который состоит из членов базового класса или классов и всех новых элементов, добавленных производным классом. В множественном наследовании можно создать граф наследования, где один и тот же базовый класс является частью нескольких производных классов. На следующем рисунке показан такой граф.  
  
 ![Несколько экземпляров базового класса](../cpp/media/vc38xn1.gif "vc38XN1")  
Несколько экземпляров одного базового класса  
  
 На рисунке представлены наглядные представления компонентов `CollectibleString` и `CollectibleSortable`. Однако базовый класс (`Collectible`) находится в `CollectibleSortableString` на протяжении путей `CollectibleString` и `CollectibleSortable`. Для устранения этой избыточности такие классы при наследовании можно объявлять как виртуальные базовые классы.  