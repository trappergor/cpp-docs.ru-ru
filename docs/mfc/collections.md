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
ms.openlocfilehash: f3dea68deaae73313fe389be49e8bbed7da3c93a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767188"
---
# <a name="collections"></a>Коллекции

Библиотеки Microsoft Foundation Class предоставляет классы коллекций для управления группами объектов. Эти классы бывают двух типов:

- [Классы коллекций, создаваемых из шаблонов C++](#_core_the_template_based_collection_classes)

- [Классы коллекций, не создан на основе шаблонов](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
>  Если код уже использует нешаблонных классов коллекций, можно продолжать их использовать. При написании новых классов типобезопасных коллекций для собственных типов данных, рекомендуется использовать более новые классы на основе шаблона.

##  <a name="_core_collection_shapes"></a> Коллекция фигур

Класс коллекции характерно «shape» и типы его элементов. Фигуры — это способ объекты организованы и хранятся в коллекции. MFC предоставляет три фигуры базовой коллекции: список, массивов и схем (также известный как словари). Вы можете выбрать фигуру коллекции, который наиболее подходит для конкретной задачи программирования.

Каждый из трех форм предоставленной коллекции описан кратко далее в этом разделе. Чтобы сравнить возможности фигур, которые помогут решить, который лучше всего подходит для вашей программы, см. в разделе [рекомендации по выбору класса коллекции](../mfc/recommendations-for-choosing-a-collection-class.md).

- Список

   Класс списка предоставляет упорядоченный и неиндексированные список элементов, реализованы в виде двунаправленного связанного списка. Список «Начало» и «хвост» и добавление или удаление элементов из головного или заключительного фрагмента, или вставки и удаления элементов в середине, выполняется очень быстро.

- Массив

   Класс array предоставляет массив объектов, динамически по размеру, заказанное и индексированных целое число.

- Карты (также известный как словарь)

   Карта — коллекция, которая связывает объект ключа с объект значения.

##  <a name="_core_the_template_based_collection_classes"></a> Классы коллекций на основе шаблона

Самый простой способ реализовать типобезопасных коллекций, который содержит объекты любого типа — для использования одного из классов MFC на основе шаблона. Примеры этих классов см. в примере MFC [СОБИРАТЬ](../overview/visual-cpp-samples.md).

В следующей таблице перечислены классы коллекций, основанных на шаблонах MFC.

### <a name="collection-template-classes"></a>Классы коллекции шаблонов

|Содержимое коллекции|Массивы|Списки|Карты|
|-------------------------|------------|-----------|----------|
|Коллекции объектов любого типа|`CArray`|`CList`|`CMap`|
|Указатели на объекты любого типа коллекции|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Классы коллекций, не на основе шаблонов

Если приложение уже использует нешаблонных классов MFC, можно продолжать их использовать. Тем не менее для новых коллекций, мы рекомендуем использовать классы на основе шаблона. В следующей таблице перечислены классы коллекций MFC, не основанных на шаблонах.

### <a name="nontemplate-collection-classes"></a>Классы коллекций нешаблонных

|Массивы|Списки|Карты|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

Характеристики классов коллекций MFC в таблицу [рекомендации по выбору класса коллекции](../mfc/recommendations-for-choosing-a-collection-class.md) описывает классы коллекций MFC с точки зрения эти характеристики (кроме фигуры):

- Использует ли класс шаблоны C++

- Можно ли сериализовать элементы, хранящиеся в коллекции

- Можно ли поместить эти элементы в дамп для диагностики

- Является ли коллекция типобезопасной

### <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

#### <a name="general-collection-class-tasks"></a>Класс коллекции общие задачи

- [Рекомендации по выбору класса коллекции](../mfc/recommendations-for-choosing-a-collection-class.md)

- [Практическое руководство. Создание безопасных типов коллекций](../mfc/how-to-make-a-type-safe-collection.md)

- [Создание коллекций стеков и очередей](../mfc/creating-stack-and-queue-collections.md)

- [CArray::Add](../mfc/reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Класс коллекции в основанных на шаблонах задачи

- [Классы на основе шаблонов](../mfc/template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Доступ к членам коллекции (на основе шаблона или нет)

- [Доступ ко всем членам коллекции](../mfc/accessing-all-members-of-a-collection.md)

- [Удаление всех объектов из коллекции CObject](../mfc/deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)
