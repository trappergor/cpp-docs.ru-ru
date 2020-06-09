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
ms.openlocfilehash: 2921fe4e4f10c96a096d30d8f842eecdfd644ca6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615909"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>удаление всех объектов из коллекции CObject

В этой статье объясняется, как удалить все объекты в коллекции (без удаления самого объекта коллекции).

Чтобы удалить все объекты из коллекции `CObject` s (или объектов, производных от `CObject` ), используйте один из методов итерации, описанных в статье доступ ко [всем элементам коллекции](accessing-all-members-of-a-collection.md) , чтобы удалить каждый из объектов в свою очередь.

> [!CAUTION]
> Объекты в коллекциях можно совместно использовать. То есть коллекция хранит указатель на объект, но другие части программы также могут иметь указатели на один и тот же объект. Необходимо избегать удаления объекта, который является общим, пока все части не будут завершать работу с объектом.

В этой статье показано, как удалить объекты в:

- [Список](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [Массив](#_core_to_delete_all_elements_in_an_array)

- [Схема](#_core_to_delete_all_elements_in_a_map)

#### <a name="to-delete-all-objects-in-a-list-of-pointers-to-cobject"></a><a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>Удаление всех объектов из списка указателей на CObject

1. Используйте `GetHeadPosition` и `GetNext` для итерации по списку.

1. Используйте оператор **Delete** , чтобы удалить каждый объект, так как он встречается в итерации.

1. Вызовите `RemoveAll` функцию, чтобы удалить все элементы из списка после удаления объектов, связанных с этими элементами.

В следующем примере показано, как удалить все объекты из списка `CPerson` объектов. Каждый объект в списке является указателем на `CPerson` объект, первоначально выделенный в куче.

[!code-cpp[NVC_MFCCollections#17](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

Последний вызов функции, `RemoveAll` , — это функция-член списка, которая удаляет все элементы из списка. Функция-член `RemoveAt` удаляет один элемент.

Обратите внимание на различие между удалением объекта элемента и удалением самого элемента. При удалении элемента из списка просто удаляется ссылка списка на объект. Объект по-прежнему существует в памяти. При удалении объекта он прекращает свое существование, а его память освобождается. Таким образом, важно удалить элемент сразу после удаления объекта, чтобы список не попытается получить доступ к объектам, которые больше не существуют.

#### <a name="to-delete-all-elements-in-an-array"></a><a name="_core_to_delete_all_elements_in_an_array"></a>Удаление всех элементов в массиве

1. Используйте `GetSize` и целочисленные значения индекса для выполнения итерации по массиву.

1. Используйте оператор **Delete** , чтобы удалить каждый элемент при его обнаружении в итерации.

1. Вызовите `RemoveAll` функцию, чтобы удалить все элементы из массива после их удаления.

   Ниже приведен код для удаления всех элементов массива.

   [!code-cpp[NVC_MFCCollections#18](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

Как и в приведенном выше примере, можно вызвать метод `RemoveAll` , чтобы удалить все элементы в массиве или `RemoveAt` удалить отдельный элемент.

#### <a name="to-delete-all-elements-in-a-map"></a><a name="_core_to_delete_all_elements_in_a_map"></a>Удаление всех элементов в сопоставлении

1. Используйте `GetStartPosition` и `GetNextAssoc` для итерации по массиву.

1. Используйте оператор **Delete** , чтобы удалить ключ и (или) значение для каждого элемента Map, так как он встречается в итерации.

1. Вызовите `RemoveAll` функцию, чтобы удалить все элементы из схемы после их удаления.

   Ниже приведен код для удаления всех элементов `CMap` коллекции. Каждый элемент в сопоставлении имеет строку в качестве ключа и `CPerson` объект (производный от `CObject` ) в качестве значения.

   [!code-cpp[NVC_MFCCollections#19](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

Можно вызвать `RemoveAll` , чтобы удалить все элементы в сопоставлении или `RemoveKey` удалить отдельный элемент с указанным ключом.

## <a name="see-also"></a>См. также раздел

[Доступ ко всем элементам коллекции](accessing-all-members-of-a-collection.md)
