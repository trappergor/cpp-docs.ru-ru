---
title: Коллекции
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- arrays [MFC], classes
- MFC collection classes
- shapes, collection
- collection classes [MFC], MFC
- collections, about collections
- array templates [MFC]
- collection classes [MFC], template-based
- collection classes [MFC], about collection classes
- collection classes [MFC], maps
- collection classes [MFC], arrays
- shapes
- collection classes [MFC], lists
- collection classes [MFC], shapes
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
ms.openlocfilehash: f2cd03afbb09dff38298454658c3d3dc2dfa6a8a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619349"
---
# <a name="collections"></a>Коллекции

Библиотека Microsoft Foundation Class предоставляет классы коллекций для управления группами объектов. Эти классы имеют два типа:

- [Классы коллекций, созданные из шаблонов C++](#_core_the_template_based_collection_classes)

- [Классы коллекций, не созданные из шаблонов](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
> Если в коде уже используются классы коллекций, не являющиеся шаблонами, их можно продолжать использовать. При написании новых классов строго типизированных коллекций для собственных типов данных рекомендуется использовать новые классы на основе шаблонов.

## <a name="collection-shapes"></a><a name="_core_collection_shapes"></a>Фигуры коллекций

Класс коллекции характеризуется его «Shape» и типами его элементов. Фигура обозначает способ упорядочения объектов и их хранения в коллекции. MFC предоставляет три основные фигуры коллекций: списки, массивы и карты (также известные как словари). Вы можете выбрать фигуру коллекции, которая наиболее подходит для конкретной задачи программирования.

Каждая из трех указанных форм коллекций описывается вкратце далее в этом разделе. Для сравнения функций фигур, которые помогут решить, что лучше подходит для вашей программы, см. раздел [рекомендации по выбору класса коллекции](recommendations-for-choosing-a-collection-class.md).

- Список

   Класс List предоставляет упорядоченный неиндексированный список элементов, реализованный в виде двунаправленного связанного списка. Список содержит «Head» и «хвост», а также добавление или удаление элементов из головного или заключительного фрагмента, а также вставка или удаление элементов в середине — очень быстро.

- Array

   Класс Array предоставляет динамически изменяемый, упорядоченный и целочисленный индексируемый массив объектов.

- Map (также известный как словарь)

   Сопоставление — это коллекция, которая связывает объект ключа с объектом значения.

## <a name="the-template-based-collection-classes"></a><a name="_core_the_template_based_collection_classes"></a>Классы коллекций на основе шаблонов

Самым простым способом реализации строго типизированной коллекции, содержащей объекты любого типа, является использование одного из классов на основе шаблона MFC. Примеры этих классов см. в разделе [Получение](../overview/visual-cpp-samples.md)образца MFC.

В следующей таблице перечислены классы коллекций на основе шаблонов MFC.

### <a name="collection-template-classes"></a>Классы шаблонов коллекций

|Содержимое коллекции|Массивы|Списки|Maps|
|-------------------------|------------|-----------|----------|
|Коллекции объектов любого типа|`CArray`|`CList`|`CMap`|
|Коллекции указателей на объекты любого типа|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

## <a name="the-collection-classes-not-based-on-templates"></a><a name="_core_the_collection_classes_not_based_on_templates"></a>Классы коллекций не основаны на шаблонах

Если в приложении уже используются классы нешаблонных классов MFC, их можно продолжать использовать. Однако для новых коллекций рекомендуется использовать классы на основе шаблонов. В следующей таблице перечислены классы коллекций MFC, которые не основаны на шаблонах.

### <a name="nontemplate-collection-classes"></a>Классы коллекций, не являющиеся шаблонами

|Массивы|Списки|Maps|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

Характеристики таблицы классов коллекций MFC в [рекомендациях по выбору класса](recommendations-for-choosing-a-collection-class.md) коллекции описывают классы коллекций MFC с точки зрения этих характеристик (кроме Shape):

- Использует ли класс шаблоны C++

- Можно ли сериализовать элементы, хранящиеся в коллекции

- Можно ли поместить эти элементы в дамп для диагностики

- Является ли коллекция типобезопасной

### <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

#### <a name="general-collection-class-tasks"></a>Общие задачи класса коллекции

- [Рекомендации по выбору класса коллекции](recommendations-for-choosing-a-collection-class.md)

- [Практическое руководство. Создание типобезопасных коллекций](how-to-make-a-type-safe-collection.md)

- [Создание коллекций стеков и очередей](creating-stack-and-queue-collections.md)

- [CArray:: Add](reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Задачи класса коллекции на основе шаблона

- [Классы на основе шаблонов](template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Доступ к членам коллекции (на основе шаблона или не)

- [Доступ ко всем элементам коллекции](accessing-all-members-of-a-collection.md)

- [удаление всех объектов из коллекции CObject](deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>См. также раздел

[Концепции](mfc-concepts.md)<br/>
[Общие разделы по MFC](general-mfc-topics.md)
