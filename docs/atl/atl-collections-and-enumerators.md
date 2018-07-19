---
title: Коллекции и перечислители ATL | Документация Майкрософт
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
ms.openlocfilehash: 9837b42148062bdd2c44855c129f085ca47cdec0
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848798"
---
# <a name="atl-collections-and-enumerators"></a>Коллекции и перечислители ATL
Объект `collection` является COM-объектом, который предоставляет интерфейс, обеспечивающий доступ к группе элементов данных (необработанных данных или другие объекты). Интерфейс, который соответствует стандартам, для предоставления доступа к группе объектов называется *интерфейс коллекции*.  
  
 Как минимум, необходимо предоставить интерфейсы коллекций `Count` свойство, которое возвращает количество элементов в коллекции, `Item` свойство, которое возвращает элемент из коллекции на основании индекса, и `_NewEnum` свойство, которое возвращает Перечислитель для коллекции. При необходимости можно предоставить интерфейсы коллекций `Add` и `Remove` методы, позволяющие элементов для вставки в или удален из коллекции и `Clear` метод для удаления всех элементов.  
  
 `enumerator` Является COM-объектом, который предоставляет интерфейс для итерационного перебора элементов коллекции. Интерфейсы перечислителя предоставляют последовательного доступа к элементам коллекции с помощью четырех требуемые методы: `Next`, `Skip`, `Reset`, и `Clone`.  
  
 Дополнительные сведения об интерфейсах перечислителя с изучения классическом (но полностью воображаемого) [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx) интерфейс.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Классы коллекций и перечислителей ATL](../atl/atl-collection-and-enumerator-classes.md)  
 Краткое описание и приводятся ссылки на классы ATL, которые помогут вам реализовать коллекции и перечислители.  
  
 [Принципы разработки интерфейсов для коллекций и перечислителей](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 Описание принципов проектирования каждого типа интерфейса.  
  
 [Реализация коллекции на основе стандартной библиотеки C++](../atl/implementing-an-stl-based-collection.md)  
 Развернутый пример, в котором описывается реализация коллекции на основе стандартной библиотеки C++.  
  
## <a name="related-sections"></a>Связанные разделы  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.  
  
 [Пример ATLCollections](../visual-cpp-samples.md)  
 Пример, демонстрирующий использование `ICollectionOnSTLImpl` и `CComEnumOnSTL`и реализация пользовательских классов политики копирования.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

