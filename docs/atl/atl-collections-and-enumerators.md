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
ms.openlocfilehash: 00265d3ce0f8ea867021500777d93991d245be47
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204817"
---
# <a name="atl-collections-and-enumerators"></a>Коллекции и перечислители ATL
Объект `collection` является COM-объектом, который предоставляет интерфейс, обеспечивающий доступ к группе элементов данных (необработанных данных или другие объекты). Интерфейс, который соответствует стандартам, для предоставления доступа к группе объектов называется *интерфейс коллекции*.  
  
 Как минимум, необходимо предоставить интерфейсы коллекций `Count` свойство, которое возвращает количество элементов в коллекции, `Item` свойство, которое возвращает элемент из коллекции на основании индекса, и `_NewEnum` свойство, которое возвращает Перечислитель для коллекции. При необходимости можно предоставить интерфейсы коллекций `Add` и `Remove` методы, позволяющие элементов для вставки в или удален из коллекции и `Clear` метод для удаления всех элементов.  
  
 `enumerator` Является COM-объектом, который предоставляет интерфейс для итерационного перебора элементов коллекции. Интерфейсы перечислителя предоставляют последовательного доступа к элементам коллекции с помощью четырех требуемые методы: `Next`, `Skip`, `Reset`, и `Clone`.  
  
 Дополнительные сведения о интерфейсы перечислителя, считывая справочные материалы по такие как [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) интерфейс.  
  
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

