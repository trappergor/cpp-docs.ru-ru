---
title: Коллекции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: beae5370c86bf0142b29f029778083f3042ae931
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345561"
---
# <a name="collections"></a>Коллекции
Библиотеки классов Microsoft Foundation предоставляет классы коллекций для управления группами объектов. Эти классы могут быть двух типов:  
  
-   [Классы коллекций, созданные на основе шаблонов C++](#_core_the_template_based_collection_classes)  
  
-   [Классы коллекций, которые не созданы на основе шаблонов](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  Если код уже использует классы коллекций нешаблонных, можно продолжать их использовать. При написании новых классов строго типизированную коллекцию для собственных типов данных, рекомендуется использовать более новые классы на основе шаблона.  
  
##  <a name="_core_collection_shapes"></a> Форма коллекции  
 Класс коллекции характеризуются «формы» и типа его элементов. Форма — это способ объекты организованы и хранятся в коллекции. MFC предоставляет три фигуры базовой коллекции: списки, массивы и сопоставляет (также известный как словари). Можно выбрать коллекцию фигуры, который наиболее подходит для конкретной задачи программирования.  
  
 Кратко далее в этом разделе описывается каждый из трех форм предоставленной коллекции. Для сравнения возможностей фигур, помогающие решить, какой наилучшим образом подходит для вашей программы. в разделе [рекомендации по выбору класса коллекции](../mfc/recommendations-for-choosing-a-collection-class.md).  
  
-   Список  
  
     List-класс предоставляет упорядоченный, неиндексированных список элементов, которые реализованы в виде двунаправленного связанного списка. Список содержит «заголовок» и «хвоста» и добавление и удаление элементов из head или хвоста, или вставка или удаление элементов в середине, очень быстро.  
  
-   Массив  
  
     Класс array предоставляет массив объектов, динамически по размеру, упорядоченные и индексировать целое число со знаком.  
  
-   Карта (также известный как словарь)  
  
     Карта представляет коллекцию, которая связывает объект ключа с объектом значения.  
  
##  <a name="_core_the_template_based_collection_classes"></a> Классы коллекций на основе шаблона  
 Самый простой способ реализации строго типизированные коллекции, которая содержит объекты любого типа является использование одного из классов MFC на основе шаблона. Примеры этих классов см. в примере MFC [СБОРА](../visual-cpp-samples.md).  
  
 Ниже перечислены классы коллекций, основанных на шаблонах MFC.  
  
### <a name="collection-template-classes"></a>Классы коллекции шаблонов  
  
|Содержимое коллекции|Массивы|Списки|Карты|  
|-------------------------|------------|-----------|----------|  
|Коллекции объектов любого типа|`CArray`|`CList`|`CMap`|  
|Коллекции указателей на объекты любого типа|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Классы коллекций, не на основе шаблонов  
 Если приложение уже использует нешаблонных классов MFC, могут продолжать их использовать. Однако для новых семейств сайтов, рекомендуется использовать классы на основе шаблона. В следующей таблице перечислены классы коллекций MFC, не основанных на шаблонах.  
  
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
  
-   Использует ли класс шаблоны C++  
  
-   Можно ли сериализовать элементы, хранящиеся в коллекции  
  
-   Можно ли поместить эти элементы в дамп для диагностики  
  
-   Является ли коллекция типобезопасной  
  
### <a name="what-do-you-want-to-do"></a>Что Вы хотите делать  
  
#### <a name="general-collection-class-tasks"></a>Класс коллекции общие задачи  
  
-   [Рекомендации по выбору класса коллекции](../mfc/recommendations-for-choosing-a-collection-class.md)  
  
-   [Практическое руководство. Создание типобезопасных коллекций](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [Создание коллекций стеков и очередей](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../mfc/reference/carray-class.md#add)  
  
#### <a name="template-based-collection-class-tasks"></a>Класс коллекции в шаблон основан на основе задач  
  
-   [Классы на основе шаблонов](../mfc/template-based-classes.md)  
  
#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Доступ к членам коллекции (на основе шаблона или нет)  
  
-   [Доступ ко всем членам коллекции](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [Удаление всех объектов из коллекции CObject](../mfc/deleting-all-objects-in-a-cobject-collection.md)  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)

