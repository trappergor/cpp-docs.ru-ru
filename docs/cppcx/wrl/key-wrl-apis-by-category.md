---
title: Основные API WRL по категориям
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: 8ac89f3286866ac61bac5ae256bdb448fe88f07d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213828"
---
# <a name="key-wrl-apis-by-category"></a>Основные API WRL по категориям

В следующих таблицах перечислены основные C++ классы, структуры, функции и макросы библиотеки шаблонов среда выполнения Windows. Конструкции в вспомогательных пространствах имен и классах опущены. Эти списки дополняют документацию по API, которая упорядочивается по пространству имен.

## <a name="classes"></a>Классы

|Title|Description|
|-----------|-----------------|
|[Класс ActivationFactory](activationfactory-class.md)|Позволяет одному или нескольким классам быть активированными средой выполнения Windows.|
|[Класс AsyncBase](asyncbase-class.md)|Реализует асинхронный конечный автомат среды выполнения Windows.|
|[Класс ClassFactory](classfactory-class.md)|Реализует базовую функциональность интерфейса `IClassFactory`.|
|[Класс ComPtr](comptr-class.md)|Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. ComPtr автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.|
|[Класс Event (библиотека шаблонов C++ среды выполнения Windows)](event-class-wrl.md)|Представляет событие.|
|[EventSource](eventsource-class.md)|Представляет событие. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий.|
|[Класс FtmBase](ftmbase-class.md)|Представляет свободнопоточный объект маршаллера.|
|[Класс HandleT](handlet-class.md)|Представляет дескриптор объекта.|
|[Класс HString](hstring-class.md)|Обеспечивает поддержку манипуляций с дескрипторами HSTRING.|
|[Класс HStringReference](hstringreference-class.md)|Представляет HSTRING, созданный из существующей строки.|
|[Класс Module](module-class.md)|Представляет коллекцию связанных объектов.|
|[Класс Module::GenericReleaseNotifier](module-genericreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.|
|[Класс Module::MethodReleaseNotifier](module-methodreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается объектом и его указателем на член метода.|
|[Класс Module::ReleaseNotifier](module-releasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в модуле.|
|[Класс RoInitializeWrapper](roinitializewrapper-class.md)|Инициализирует среда выполнения Windows.|
|[Класс RuntimeClass](runtimeclass-class.md)|Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.|
|[Класс SimpleActivationFactory](simpleactivationfactory-class.md)|Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.|
|[Класс SimpleClassFactory](simpleclassfactory-class.md)|Предоставляет основной механизм для создания базового класса.|
|[Класс WeakRef](weakref-class.md)|Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|

## <a name="structures"></a>Структуры

|Title|Description|
|-----------|-----------------|
|[Структура ChainInterfaces](chaininterfaces-structure.md)|Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.|
|[Структура CloakedIid](cloakediid-structure.md)|Указывает на шаблоны `RuntimeClass`, `Implements` и `ChainInterfaces`, которые указанный интерфейс недоступен в списке IID.|
|[Структура Implements](implements-structure.md)|Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.|
|[Структура MixIn](mixin-structure.md)|Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.|

## <a name="functions"></a>Функции

|Title|Description|
|-----------|-----------------|
|[Функция ActivateInstance](activateinstance-function.md)|Регистрирует и извлекает экземпляр указанного типа, определенного в указанном ИДЕНТИФИКАТОРе класса.|
|[Функция AsWeak](asweak-function.md)|Извлекает слабую ссылку на определенный экземпляр.|
|[Функция обратного вызова](callback-function-wrl.md)|Создает объект, функция-член которого является методом обратного вызова.|
|[Функция CreateActivationFactory](createactivationfactory-function.md)|Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.|
|[Функция CreateClassFactory](createclassfactory-function.md)|Создает фабрику, которая создает экземпляры указанного класса.|
|[Функция GetActivationFactory](getactivationfactory-function.md)|Извлекает фабрику активации для типа, указанного в параметре шаблона.|
|[Функция Make](make-function.md)|Инициализирует указанный класс среда выполнения Windows.|

## <a name="macros"></a>Макросы

|Title|Description|
|-----------|-----------------|
|[Макрос ActivatableClass](activatableclass-macros.md)|Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса.|
|[Макрос InspectableClass](inspectableclass-macro.md)|Задает имя класса среды выполнения и уровень доверия.|

## <a name="see-also"></a>См. также раздел

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)
