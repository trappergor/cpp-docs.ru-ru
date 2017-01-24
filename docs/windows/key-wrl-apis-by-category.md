---
title: "Основные API WRL по категориям | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Основные API WRL по категориям
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующих таблицах перечислены основной [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] классы, структуры, функции и макросы. Конструкции в вспомогательные пространства имен и классы, опущены. Эти списки дополняют документацию API, которая организована по пространствам имен.  
  
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
|[Класс HandleT](../Topic/HandleT%20Class.md)|Представляет дескриптор объекта.|  
|[Класс HString](../windows/hstring-class.md)|Предоставляет поддержку для управления дескрипторы HSTRING.|  
|[Класс HStringReference](../windows/hstringreference-class.md)|Представляет HSTRING, созданной из существующей строки.|  
|[Класс модулей](../windows/module-class.md)|Представляет коллекцию связанных объектов.|  
|[Класс Module::GenericReleaseNotifier](../windows/module-genericreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.|  
|[Класс Module::MethodReleaseNotifier](../Topic/Module::MethodReleaseNotifier%20Class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик события определяется объектом и его элементом указателя на метод.|  
|[Класс Module::ReleaseNotifier](../Topic/Module::ReleaseNotifier%20Class.md)|Вызывает обработчик событий при освобождении последнего объекта в модуле.|  
|[Класс RoInitializeWrapper](RoInitializeWrapper%20Class.md)|Инициализирует объект [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[Класс RuntimeClass](../windows/runtimeclass-class.md)|Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.|  
|[Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)|Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.|  
|[Класс SimpleClassFactory](../windows/simpleclassfactory-class.md)|Предоставляет основной механизм для создания базового класса.|  
|[Класс WeakRef](../windows/weakref-class.md)|Представляет *слабую ссылку* может использоваться только средой выполнения Windows, не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|  
  
### <a name="structures"></a>Структуры  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Структура ChainInterfaces](../windows/chaininterfaces-structure.md)|Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.|  
|[Структура CloakedIid](../windows/cloakediid-structure.md)|Указывает `RuntimeClass`, `Implements` и `ChainInterfaces` указанный интерфейс недоступен в списке IID шаблоны.|  
|[Структура Implements](../Topic/Implements%20Structure.md)|Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.|  
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
|[Make-функция](../windows/make-function.md)|Инициализирует указанный класс [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
  
### <a name="macros"></a>Макросы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Макрос Activatableclass](../Topic/ActivatableClass%20Macros.md)|Заполняет внутренний кэш, содержащий фабрику, можно создать экземпляр указанного класса.|  
|[Макрос InspectableClass](../windows/inspectableclass-macro.md)|Задает уровень имя и доверия класса среды выполнения.|  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)