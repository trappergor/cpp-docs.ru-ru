---
title: "Базовые классы | Документы Microsoft"
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
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6b08321ffb027901683a4f85960579625ce98cc2
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="base-classes"></a>Базовые классы
Процесс наследования создает новый производный класс, который состоит из членов базового класса или классов и всех новых элементов, добавленных производным классом. В множественном наследовании можно создать граф наследования, где один и тот же базовый класс является частью нескольких производных классов. На следующем рисунке показан такой граф.  
  
 ![Несколько экземпляров базового класса](../cpp/media/vc38xn1.gif "vc38XN1")  
Несколько экземпляров одного базового класса  
  
 На рисунке представлены наглядные представления компонентов `CollectibleString` и `CollectibleSortable`. Однако базовый класс (`Collectible`) находится в `CollectibleSortableString` на протяжении путей `CollectibleString` и `CollectibleSortable`. Для устранения этой избыточности такие классы при наследовании можно объявлять как виртуальные базовые классы.  
  

