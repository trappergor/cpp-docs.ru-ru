---
title: Коллекции и перечислители ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 537d7e8b7264beddc68805ab8b8dec2ce7883859
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-collections-and-enumerators"></a>Коллекции и перечислители ATL
Объект `collection` COM-объектом, который предоставляет интерфейс, обеспечивающий доступ к группе элементов данных (необработанные данные или другие объекты). Интерфейс, который соответствует стандартам, для предоставления доступа к группе объектов называется *интерфейс коллекции*.  
  
 Как минимум, необходимо предоставить интерфейсы коллекций **число** свойство, которое возвращает количество элементов в коллекции, **элемент** свойство, которое возвращает элемент из коллекции по индексу и `_NewEnum` свойство, которое возвращает перечислитель для коллекции. При необходимости можно предоставить интерфейсы коллекций **добавить** и **удалить** методы, позволяющие элементов для вставлены или удалены из коллекции и **снимите** метод для удаления все элементы.  
  
 `enumerator` COM-объектом, который предоставляет интерфейс для перебора элементов коллекции. Интерфейсы перечислителя обеспечивают последовательный доступ к элементам коллекции посредством четыре требуемые методы: `Next`, **пропустить**, **Сброс**, и `Clone`.  
  
 Дополнительные сведения об интерфейсах перечислитель путем чтения о классическом (но полностью мнимой) [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx) интерфейса.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Классы коллекций и перечислителей ATL](../atl/atl-collection-and-enumerator-classes.md)  
 Краткое описание и предоставляет ссылки на классы ATL, которые помогут при реализации коллекции и перечислители.  
  
 [Принципы разработки интерфейсов для коллекций и перечислителей](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 Описывает принципы другую структуру каждого типа интерфейса.  
  
 [Реализация коллекции на основе стандартной библиотеки C++](../atl/implementing-an-stl-based-collection.md)  
 Расширенный пример, в котором описывается реализация коллекций на основе стандартной библиотеки C++.  
  
## <a name="related-sections"></a>Связанные разделы  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.  
  
 [Образец ATLCollections](../visual-cpp-samples.md)  
 Пример, демонстрирующий использование `ICollectionOnSTLImpl` и `CComEnumOnSTL`и реализация пользовательских классов политики копирования.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

