---
title: "Пространство имен Microsoft::WRL | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL"
  - "module/Microsoft::WRL"
  - "async/Microsoft::WRL"
  - "internal/Microsoft::WRL"
  - "event/Microsoft::WRL"
  - "ftm/Microsoft::WRL"
  - "client/Microsoft::WRL"
  - "corewrappers/Microsoft::WRL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WRL - пространство имен"
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пространство имен Microsoft::WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет основные типы, входящие в состав [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Microsoft::WRL;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="typedefs"></a>Определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt &#124; InhibitWeakReference>`|  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс ActivationFactory](../windows/activationfactory-class.md)|Позволяет одному или нескольким классам быть активированными средой выполнения Windows.|  
|[Класс AsyncBase](../windows/asyncbase-class.md)|Реализует асинхронный конечный автомат среды выполнения Windows.|  
|[Класс ClassFactory](../windows/classfactory-class.md)|Реализует базовую функциональность интерфейса `IClassFactory`.|  
|[Класс ComPtr](../windows/comptr-class.md)|Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. ComPtr автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.|  
|[Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)|Класс шаблона, используемый для типов аргументов событий для задержек.|  
|[Класс EventSource](../windows/eventsource-class.md)|Представляет событие. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий.|  
|[Класс FtmBase](../windows/ftmbase-class.md)|Представляет свободнопоточный объект маршаллера.|  
|[Класс модулей](../windows/module-class.md)|Представляет коллекцию связанных объектов.|  
|[Класс RuntimeClass](../windows/runtimeclass-class.md)|Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.|  
|[Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)|Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.|  
|[Класс SimpleClassFactory](../windows/simpleclassfactory-class.md)|Предоставляет основной механизм для создания базового класса.|  
|[Класс WeakRef](../windows/weakref-class.md)|Представляет *слабую ссылку* может использоваться только средой выполнения Windows, не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|  
  
### <a name="structures"></a>Структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура ChainInterfaces](../windows/chaininterfaces-structure.md)|Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.|  
|[Структура CloakedIid](../windows/cloakediid-structure.md)|Указывает шаблонам RuntimeClass, Implements и ChainInterfaces, что заданный интерфейс недоступен в списке IID.|  
|[Структура Implements](../Topic/Implements%20Structure.md)|Реализует QueryInterface и GetIid для указанных интерфейсов.|  
|[Структура MixIn](../windows/mixin-structure.md)|Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.|  
|[Структура RuntimeClassFlags](../windows/runtimeclassflags-structure.md)|Содержит тип экземпляра [RuntimeClass](../windows/runtimeclass-class.md).|  
  
### <a name="enumerations"></a>Перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление AsyncResultType](../windows/asyncresulttype-enumeration.md)|Указывает тип результата, возвращаемого методом GetResults().|  
|[Перечисление ModuleType](../Topic/ModuleType%20Enumeration.md)|Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.|  
|[Перечисление RuntimeClassType](../windows/runtimeclasstype-enumeration.md)|Указывает тип [RuntimeClass](../windows/runtimeclass-class.md) экземпляр, который поддерживается.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция AsWeak](../windows/asweak-function.md)|Извлекает слабую ссылку на определенный экземпляр.|  
|[Функция обратного вызова](../windows/callback-function-windows-runtime-cpp-template-library.md)|Создает объект, функция-член которого является методом обратного вызова.|  
|[Функция CreateActivationFactory](../windows/createactivationfactory-function.md)|Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.|  
|[Функция CreateClassFactory](../windows/createclassfactory-function.md)|Создает фабрику, которая создает экземпляры указанного класса.|  
|[Make-функция](../windows/make-function.md)|Инициализирует указанный класс [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)