---
title: "Удаление всех объектов из коллекции CObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8065af989f220f5954b851149c1b7c7a814a7d1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>удаление всех объектов из коллекции CObject
В этой статье объясняется, как удалить все объекты в коллекции (без удаления самого объекта коллекции).  
  
 Чтобы удалить все объекты в коллекции `CObject`s (или объектов, производных от `CObject`), используется один из способов итерации, описанное в статье [доступ всех членов коллекции](../mfc/accessing-all-members-of-a-collection.md) удаление каждого объекта в Включите.  
  
> [!CAUTION]
>  Объекты в коллекции можно использовать совместно. То есть коллекции сохраняет указатель на объект, но другие части программы также могут иметься указатели на тот же объект. Будьте внимательны при удалении объекта, с которым до завершения всех частей с помощью объекта.  
  
 В этой статье показано, как удалить объекты в:  
  
-   [Список](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [Массив](#_core_to_delete_all_elements_in_an_array)  
  
-   [Карта](#_core_to_delete_all_elements_in_a_map)  
  
#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>Чтобы удалить все объекты в список указателей на CObject  
  
1.  Используйте `GetHeadPosition` и `GetNext` для перечисления элементов списка.  
  
2.  Используйте **удалить** оператор, чтобы удалить каждого объекта, так как оно встречается в итерации.  
  
3.  Вызовите `RemoveAll` функции, чтобы удалить все элементы из списка, после удаления объектов, связанных с этими элементами.  
  
 В следующем примере показано, как удалить все объекты из списка `CPerson` объектов. Каждый объект в списке является указателем на `CPerson` объект, который первоначально был выделен в куче.  
  
 [!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]  
  
 Последнем вызове функции `RemoveAll`, является функцией-членом списка, удаляет все элементы из списка. Функция-член `RemoveAt` Удаляет один элемент.  
  
 Обратите внимание на разницу между удаление объекта элемента и самого элемента. Удаление элемента из списка просто удаляет ссылку на объект в списке. Объект все еще существует в памяти. При удалении объекта, он перестает существовать и освобождения памяти. Таким образом важно удалить элемент сразу после удаления элемента объекта, чтобы список не пытались получить доступ к объектам, которые больше не существуют.  
  
#### <a name="_core_to_delete_all_elements_in_an_array"></a>Чтобы удалить все элементы в массиве  
  
1.  Используйте `GetSize` и целочисленных значений индекса для перечисления элементов массива.  
  
2.  Используйте **удалить** оператор, чтобы удалить каждый элемент, так как оно встречается в итерации.  
  
3.  Вызовите `RemoveAll` функции, чтобы удалить все элементы из массива после их удаления.  
  
     Ниже приведен код для удаления всех элементов в массиве:  
  
     [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]  
  
 Как в приведенном выше примере список, можно вызвать `RemoveAll` для удаления всех элементов в массиве или `RemoveAt` для удаления отдельных элементов.  
  
#### <a name="_core_to_delete_all_elements_in_a_map"></a>Чтобы удалить все элементы на карте  
  
1.  Используйте `GetStartPosition` и `GetNextAssoc` для перечисления элементов массива.  
  
2.  Используйте **удалить** оператор, чтобы удалить ключ и значение для каждого элемента карты, так как оно встречается в итерации.  
  
3.  Вызовите `RemoveAll` функции, чтобы удалить все элементы из карты после их удаления.  
  
     Код для удаления всех элементов `CMap` коллекция является следующим образом. Каждый элемент в схеме, имеет строку в качестве ключа и `CPerson` объектов (производный от `CObject`) как значение.  
  
     [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]  
  
 Можно вызвать `RemoveAll` для удаления всех элементов на карте или `RemoveKey` удаление отдельного элемента с указанным ключом.  
  
## <a name="see-also"></a>См. также  
 [Доступ ко всем членам коллекции](../mfc/accessing-all-members-of-a-collection.md)

