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
ms.openlocfilehash: 3fba3a3c6cd3fecbda7f46575b1d72c450c44019
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361869"
---
# <a name="collections"></a>Коллекции

Библиотека класса Microsoft Foundation предоставляет классы коллекций для управления группами объектов. Эти классы имеют два типа:

- [Классы коллекции, созданные по шаблонам СЗ](#_core_the_template_based_collection_classes)

- [Классы коллекции, не созданные из шаблонов](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
> Если в коде уже используются классы нешаблонной коллекции, вы можете продолжать их использовать. Если вы пишете новые классы сбора безопасных типов для собственных типов данных, мы рекомендуем использовать новые классы на основе шаблонов.

## <a name="collection-shapes"></a><a name="_core_collection_shapes"></a>Формы коллекции

Класс коллекции характеризуется своей «формой» и типами элементов. Форма относится к тому, как объекты организованы и хранятся в коллекции. MFC предоставляет три основные формы коллекции: списки, массивы и карты (также известные как словари). Вы можете выбрать форму коллекции, которая больше всего подходит для вашей конкретной проблемы программирования.

Каждая из трех представленных форм коллекции кратко описана позже в этой теме. Чтобы сравнить особенности фигур, чтобы помочь вам решить, что лучше для [вашей](../mfc/recommendations-for-choosing-a-collection-class.md)программы, см.

- Список

   Класс списка предоставляет упорядоченный, неиндексированный список элементов, реализованный как вдвойне связанный список. Список имеет "голову" и "хвост", и добавление или удаление элементов из головы или хвоста, или вставки или удаление элементов в середине, очень быстро.

- Array

   Класс массива обеспечивает динамически размер, упорядоченный и целотый индексированный массив объектов.

- Карта (также известная как словарь)

   Карта — это коллекция, которая связывает ключевой объект с объектом значения.

## <a name="the-template-based-collection-classes"></a><a name="_core_the_template_based_collection_classes"></a>Классы коллекции на основе шаблонов

Самый простой способ реализации коллекции безопасности типов, содержащей объекты любого типа, — использовать один из классов, основанных на шаблонах MFC. Для примеров этих классов см. [COLLECT](../overview/visual-cpp-samples.md)

В следующей таблице перечислены классы коллекций на основе шаблонов MFC.

### <a name="collection-template-classes"></a>Классы шаблонов коллекции

|Содержимое коллекции|Массивы|Списки|Maps|
|-------------------------|------------|-----------|----------|
|Коллекции объектов любого типа|`CArray`|`CList`|`CMap`|
|Коллекции указателей на объекты любого типа|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

## <a name="the-collection-classes-not-based-on-templates"></a><a name="_core_the_collection_classes_not_based_on_templates"></a>Классы коллекции, не основанные на шаблонах

Если приложение уже использует классы MFC, вы можете продолжать их использовать. Однако для новых коллекций мы рекомендуем использовать классы на основе шаблонов. В следующей таблице перечислены классы коллекции MFC, которые не основаны на шаблонах.

### <a name="nontemplate-collection-classes"></a>Нешаблонные классы коллекций

|Массивы|Списки|Maps|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

Характеристики таблицы классов сбора MFC в [Рекомендациях по выбору класса коллекции](../mfc/recommendations-for-choosing-a-collection-class.md) описывают классы коллекции MFC с точки зрения этих характеристик (кроме формы):

- Использует ли класс шаблоны C++

- Можно ли сериализовать элементы, хранящиеся в коллекции

- Можно ли поместить эти элементы в дамп для диагностики

- Является ли коллекция типобезопасной

### <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

#### <a name="general-collection-class-tasks"></a>Задачи общего сбора-класса

- [Рекомендации по выбору класса коллекции](../mfc/recommendations-for-choosing-a-collection-class.md)

- [Практическое руководство. Создание типобезопасных коллекций](../mfc/how-to-make-a-type-safe-collection.md)

- [Создание коллекций стеков и очередей](../mfc/creating-stack-and-queue-collections.md)

- [CArray::Добавить](../mfc/reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Задачи на основе шаблонов коллекции-класса

- [Классы на основе шаблонов](../mfc/template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Доступ к членам коллекции (На основе шаблонов или нет)

- [Доступ ко всем членам коллекции](../mfc/accessing-all-members-of-a-collection.md)

- [удаление всех объектов из коллекции CObject](../mfc/deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>См. также раздел

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие темы МФЦ](../mfc/general-mfc-topics.md)
