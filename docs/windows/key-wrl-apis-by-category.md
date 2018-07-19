---
title: Основные API WRL по категориям | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9936c85443f893111b3c2b9de17ca80e6fb382b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881462"
---
# <a name="key-wrl-apis-by-category"></a>Основные API WRL по категориям
В следующих таблицах перечислены первичного классы, структуры, функции и макросы библиотека шаблонов C++ среды выполнения Windows. Конструкции в вспомогательного пространства имен и классы, опущены. Эти списки дополнять документацию по API, упорядоченных по пространствам имен.  
  
### <a name="classes"></a>Классы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Класс ActivationFactory](../windows/activationfactory-class.md)|Позволяет одному или нескольким классам быть активированными средой выполнения Windows.|  
|[Класс AsyncBase](../windows/asyncbase-class.md)|Реализует асинхронный конечный автомат среды выполнения Windows.|  
|[Класс ClassFactory](../windows/classfactory-class.md)|Реализует базовую функциональность интерфейса `IClassFactory`.|  
|[Класс ComPtr](../windows/comptr-class.md)|Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. ComPtr автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.|  
|[Класс Event (библиотека шаблонов C++ среды выполнения Windows)](../windows/event-class-windows-runtime-cpp-template-library.md)|Представляет событие.|  
|[Класс EventSource](../windows/eventsource-class.md)|Представляет событие. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий.|  
|[Класс FtmBase](../windows/ftmbase-class.md)|Представляет свободнопоточный объект маршаллера.|  
|[Класс HandleT](../windows/handlet-class.md)|Представляет дескриптор объекта.|  
|[Класс HString](../windows/hstring-class.md)|Предоставляет поддержку для управления дескрипторов HSTRING.|  
|[Класс HStringReference](../windows/hstringreference-class.md)|Представляет HSTRING, созданной из существующей строки.|  
|[Класс Module](../windows/module-class.md)|Представляет коллекцию связанных объектов.|  
|[Класс Module::GenericReleaseNotifier](../windows/module-genericreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.|  
|[Класс Module::MethodReleaseNotifier](../windows/module-methodreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается объектом и его элементом указателя для метода.|  
|[Класс Module::ReleaseNotifier](../windows/module-releasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в модуле.|  
|[Класс RoInitializeWrapper](../windows/roinitializewrapper-class.md)|Инициализирует среду выполнения Windows.|  
|[Класс RuntimeClass](../windows/runtimeclass-class.md)|Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.|  
|[Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)|Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.|  
|[Класс SimpleClassFactory](../windows/simpleclassfactory-class.md)|Предоставляет основной механизм для создания базового класса.|  
|[Класс WeakRef](../windows/weakref-class.md)|Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|  
  
### <a name="structures"></a>Структуры  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Структура ChainInterfaces](../windows/chaininterfaces-structure.md)|Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.|  
|[Структура CloakedIid](../windows/cloakediid-structure.md)|Указывает `RuntimeClass`, `Implements` и `ChainInterfaces` шаблоны, заданный интерфейс недоступен в списке IID.|  
|[Структура Implements](../windows/implements-structure.md)|Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.|  
|[Структура MixIn](../windows/mixin-structure.md)|Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.|  
  
### <a name="functions"></a>Функции  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Функция ActivateInstance](../windows/activateinstance-function.md)|Регистрирует и извлекает экземпляр заданного типа, определенного в идентификатор указанного класса.|  
|[Функция AsWeak](../windows/asweak-function.md)|Извлекает слабую ссылку на определенный экземпляр.|  
|[Функция обратного вызова](../windows/callback-function-windows-runtime-cpp-template-library.md)|Создает объект, функция-член которого является методом обратного вызова.|  
|[Функция CreateActivationFactory](../windows/createactivationfactory-function.md)|Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.|  
|[Функция CreateClassFactory](../windows/createclassfactory-function.md)|Создает фабрику, которая создает экземпляры указанного класса.|  
|[Функция GetActivationFactory](../windows/getactivationfactory-function.md)|Извлекает фабрику активации для типа, указанного в параметре шаблона.|  
|[Функция Make](../windows/make-function.md)|Инициализирует указанный класс среды выполнения Windows.|  
  
### <a name="macros"></a>Макросы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Макрос ActivatableClass](../windows/activatableclass-macros.md)|Заполняет внутренний кэш, который содержит фабрику, можно создать экземпляр указанного класса.|  
|[Макрос InspectableClass](../windows/inspectableclass-macro.md)|Задает уровень имя и доверия класса среды выполнения.|  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)