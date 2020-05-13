---
title: удаление всех объектов из коллекции CObject
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
ms.openlocfilehash: 303b8a566a730c5abd06d51fb7977174e19a6435
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370539"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>удаление всех объектов из коллекции CObject

В этой статье объясняется, как удалить все объекты в коллекции (без удаления самого объекта коллекции).

Чтобы удалить все объекты `CObject`в коллекции s (или объектов, полученных из), `CObject`вы используете один из методов итерации, описанных в статье Доступ ко всем членам [коллекции,](../mfc/accessing-all-members-of-a-collection.md) чтобы удалить каждый объект в свою очередь.

> [!CAUTION]
> Объекты в коллекциях могут быть общими. То есть коллекция сохраняет указатель на объект, но другие части программы могут также иметь указатели на тот же объект. Вы должны быть осторожны, чтобы не удалить объект, который является общим до тех пор, пока все части закончили с помощью объекта.

В этой статье показано, как удалить объекты в:

- [Список](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [Массив](#_core_to_delete_all_elements_in_an_array)

- [Карта](#_core_to_delete_all_elements_in_a_map)

#### <a name="to-delete-all-objects-in-a-list-of-pointers-to-cobject"></a><a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>Удалить все объекты в списке указателей на CObject

1. `GetHeadPosition` Используйте `GetNext` и итерировать через список.

1. Используйте оператора **удаления,** чтобы удалить каждый объект, как он встречается в итерации.

1. Вызов `RemoveAll` функции для удаления всех элементов из списка после того, как объекты, связанные с этими элементами, были удалены.

В следующем примере показано, как удалить `CPerson` все объекты из списка объектов. Каждый объект в списке является `CPerson` указателем на объект, который был первоначально выделен на куче.

[!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

Последний вызов `RemoveAll`функции, это функция элемента списка, которая удаляет все элементы из списка. Функция `RemoveAt` члена удаляет один элемент.

Обратите внимание на разницу между удалением объекта элемента и удалением самого элемента. Удаление элемента из списка просто удаляет ссылку списка на объект. Объект все еще существует в памяти. Когда вы удаляете объект, он перестает существовать и его память устраняется. Таким образом, важно удалить элемент сразу после удаления объекта элемента, чтобы список не пытался получить доступ к объектам, которые больше не существуют.

#### <a name="to-delete-all-elements-in-an-array"></a><a name="_core_to_delete_all_elements_in_an_array"></a>Удаление всех элементов в массиве

1. Использование `GetSize` и целые значения индекса для итерирования через массив.

1. Используйте оператора **удаления,** чтобы удалить каждый элемент, как он встречается в итерации.

1. Вызов `RemoveAll` функции, чтобы удалить все элементы из массива после их удаления.

   Код для удалять все элементы массива:

   [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

Как и в приведенном выше `RemoveAll` примере списка, можно `RemoveAt` вызвать все элементы в массиве или удалить отдельный элемент.

#### <a name="to-delete-all-elements-in-a-map"></a><a name="_core_to_delete_all_elements_in_a_map"></a>Удаление всех элементов на карте

1. `GetStartPosition` Используйте `GetNextAssoc` и итерировать через массив.

1. Используйте оператора **удаления,** чтобы удалить ключ и/или значение для каждого элемента карты, как это встречается в итерации.

1. Вызов `RemoveAll` функции, чтобы удалить все элементы с карты после их удаления.

   Код для удаляния всех `CMap` элементов коллекции является следующим образом. Каждый элемент на карте имеет строку `CPerson` в качестве `CObject`ключа и объект (производный от ) в качестве значения.

   [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

Вы можете `RemoveAll` позвонить, чтобы удалить `RemoveKey` все элементы на карте или удалить отдельный элемент с указанным ключом.

## <a name="see-also"></a>См. также раздел

[Доступ ко всем членам коллекции](../mfc/accessing-all-members-of-a-collection.md)
