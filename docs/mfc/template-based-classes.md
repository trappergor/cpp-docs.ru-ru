---
title: Классы на основе шаблонов
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections
- CTypedPtrList class [MFC], template-based classes
- arrays [MFC], classes
- arrays [MFC], pointers
- typed pointers, collections of
- arrays [MFC], template-based
- CArray class [MFC], template-based classes
- simple template-based collections
- simple array collection classes [MFC]
- typed pointers
- collections, typed-pointer
- CList class [MFC], template-based classes
- collection classes [MFC], template-based
- CTypedPtrMap class [MFC], template-based classes
- pointers, collections of typed
- CTypedPtrArray class [MFC], template-based classes
- MFC collection classes [MFC], template-based
- template-based collection classes [MFC]
- simple list collection classes [MFC]
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
ms.openlocfilehash: 29f5f815b62835aedbca1f79b797f826ea53d83b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370459"
---
# <a name="template-based-classes"></a>Классы на основе шаблонов

В этой статье разъясняют классы сбора на основе шаблонов на основе типов на основе типов в версии MFC 3.0 и позже. Использование этих шаблонов для создания коллекций, безопасных для типов, является более удобным и помогает обеспечить безопасность типа более эффективно, чем использование классов коллекции, не основанных на шаблонах.

МФЦ предопределяет две категории коллекций на основе шаблонов:

- [Простой массив, список и классы карт](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [Массивы, списки и карты набранных указателей](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

Простые классы коллекции все `CObject`выведены из класса, поэтому они наследуют `CObject`сериализации, динамическое создание, и другие свойства . Типы сбора набранных указателей требуют, чтобы вы указали класс, который вы получаете из - `CPtrList` который `CPtrArray`должен быть одним из нешаблонных коллекций указателей, предопределенных MFC, таких как или . Ваш новый класс коллекции наследует из указанного базового класса, а функции нового класса используют инкапсулированные вызовы для членов базового класса для обеспечения безопасности типа.

Для получения более подробной информации о шаблонах СЗ [см.](../cpp/templates-cpp.md) *C++ Language Reference*

## <a name="using-simple-array-list-and-map-templates"></a><a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a>Использование шаблонов простого массива, списка и карты

Чтобы использовать простые шаблоны сбора, необходимо знать, какие данные можно хранить в этих коллекциях и какие параметры использовать в декларациях о сборе.

### <a name="simple-array-and-list-usage"></a><a name="_core_simple_array_and_list_usage"></a>Простое использование массива и списка

Простой массив и список классов, [CArray](../mfc/reference/carray-class.md) и [CList](../mfc/reference/clist-class.md), принять два параметра: *TYPE* и `ARG_TYPE`. Эти классы могут хранить любой тип данных, который вы указываете в параметре *TYPE:*

- Фундаментальные типы данных СЗЗ, такие как **int,** **char**и **float**

- Структуры и классы СЗ

- Другие типы, которые вы определяете

Для удобства и эффективности можно использовать *ARG_TYPE* параметр для определения типа аргументов функции. Как правило, вы указываете *ARG_TYPE* в качестве ссылки на тип, указанный в параметре *TYPE.* Пример:

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

Первый пример объявляет массив `myArray`коллекции, который содержит **Int**s. Второй пример объявляет коллекцию `myList`списка, `CPerson` которая хранит объекты. Некоторые функции членов классов собрания используют аргументы, тип которых указан параметром *шаблона ARG_TYPE.* Например, `Add` функция элемента `CArray` класса принимает *ARG_TYPE* аргумент:

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

### <a name="simple-map-usage"></a><a name="_core_simple_map_usage"></a>Простое использование карты

Простой класс карты, [CMap](../mfc/reference/cmap-class.md), занимает четыре параметра: *KEY*, *ARG_KEY,* *VALUE,* и *ARG_VALUE.* Как и классы массивов и список, классы карт могут хранить любой тип данных. В отличие от массивов и списков, которые индексируют и заказывают данные, которые они хранят, карты связывают ключи и значения: Вы получаете доступ к значению, хранящейся на карте, указывая связанный ключ значения. Параметр *KEY* определяет тип данных ключей, используемых для доступа к данным, хранящимся на карте. Если тип *KEY* является структурой или классом, *то параметр ARG_KEY* обычно является отсылкой к типу, указанному в *KEY.* Параметр *VALUE* определяет тип элементов, хранящихся на карте. Если тип *ARG_VALUE* является структурой или классом, то параметр *ARG_VALUE* обычно является отсылкой к типу, указанному в *VALUE.* Пример:

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

Первый пример `MY_STRUCT` хранит значения, получает к ним доступ по `MY_STRUCT` клавишам **int** и возвращает доступ к элементам по ссылке. Второй пример `CPerson` хранит значения, получает `CString` доступ к ним по ключам и возвращает ссылки на доступные элементы. Этот пример может представлять собой простую адресную книгу, в которой вы ищете людей по фамилии.

Поскольку *KEY* параметр KEY `CString` имеет тип, а `LPCSTR` *KEY_TYPE* параметр типа, ключи хранятся на карте как `SetAt` элементы типа, `LPCSTR` `CString` но упоминаются в таких функциях, как через указатели типа. Пример:

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

## <a name="using-typed-pointer-collection-templates"></a><a name="_core_using_typed.2d.pointer_collection_templates"></a>Использование шаблонов коллекции Typed-Pointer

Чтобы использовать шаблоны сбора набранных указателей, необходимо знать, какие данные можно хранить в этих коллекциях и какие параметры использовать в декларациях о сборе.

### <a name="typed-pointer-array-and-list-usage"></a><a name="_core_typed.2d.pointer_array_and_list_usage"></a>Набранный-указательный массив и использование списка

Массив набранных указателей и классов списка, [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) и [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), принимают два параметра: *BASE_CLASS* и *TYPE*. Эти классы могут хранить любой тип данных, который вы указываете в параметре *TYPE.* Они являются производными от одного из классов коллекции нешаблонов, которые хранят указатели; вы указываете этот базовый класс в *BASE_CLASS*. Для массивов используйте либо `CObArray` `CPtrArray`или . Для списков, `CObList` `CPtrList`используйте либо или .

По сути, когда вы объявляете `CObList`коллекцию на основе, скажем, нового класса не только наследует членов своего базового класса, но он также объявляет ряд дополнительных типов безопасных функций члена и операторов, которые помогают обеспечить безопасность типа путем инкапсулирования вызовов для членов базового класса. Эти инкапсуляции управляют всеми необходимыми преобразованиями типа. Пример:

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

Первый пример объявляет набор указателей массива, `myArray`, `CObArray`полученных из . Массив хранит и возвращает `CPerson` указатели `CPerson` на объекты (где класс, полученный из). `CObject` Вы можете `CObArray` позвонить в любую функцию участника, `GetAt` `ElementAt` или вы можете позвонить в новый тип-безопасной и функции или использовать **тип-безопасный** оператор.

Второй пример объявляет список набранных `myList`указателей, `CPtrList`полученный из . Список хранит и возвращает `MY_STRUCT` указатели на объекты. Класс, основанный на `CPtrList` используется для хранения указателей на `CObject`объекты, не полученные из . `CTypedPtrList`имеет ряд типов-безопасных функций `GetTail` `RemoveHead`члена: `GetHead` `GetPrev`, `GetAt`, `RemoveTail`, `GetNext`, и .

### <a name="typed-pointer-map-usage"></a><a name="_core_typed.2d.pointer_map_usage"></a>Использование карты Typed-Pointer

Тип набранного указателя класса карты, [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), принимает три параметра: *BASE_CLASS,* *KEY*и *VALUE*. В *BASE_CLASS* параметр ежевидного класса, из `CMapPtrToWord`которого можно получить новый класс: `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr` `CMapStringToOb`, и так далее. *KEY* аналогисто `CMap` *KEY* в : Он определяет тип ключа, используемого для поиска. *VALUE* аналогична `CMap` *VALUE* в : Он определяет тип объекта, хранящегося на карте. Пример:

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

Первым примером является карта `CMapPtrToPtr` на `CString` основе - он использует `MY_STRUCT`ключи, отображаемые для указателей на . Вы можете найти сохраненную указатель, позвонив в функцию безопасного `Lookup` для типа участника. Вы можете использовать **оператора** для поиска хранимых указателей и добавления его, если он не найден. И вы можете итерировать карту с `GetNextAssoc` помощью функции безопасной типа. Вы также можете позвонить `CMapPtrToPtr`другим функциям-членам класса.

Вторым примером является карта `CMapStringToOb` на основе - он использует строки клавиши, отображаемые для хранения указателей на `CMyObject` объекты. Вы можете использовать те же тип-безопасные члены, описанные `CMapStringToOb`в предыдущем пункте, или вы можете позвонить членам класса.

> [!NOTE]
> Если для параметра *VALUE* указан **тип класса** или **структуры,** а не указатель или ссылка на тип, класс или структура должны иметь конструктор копии.

Для получения дополнительной [How to Make a Type-Safe Collection](../mfc/how-to-make-a-type-safe-collection.md)информации см.

## <a name="see-also"></a>См. также раздел

[Коллекции](../mfc/collections.md)
