---
title: "Пространство имен Microsoft::WRL::Details | Microsoft Docs"
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
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пространство имен Microsoft::WRL::Details
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс ComPtrRef](../Topic/ComPtrRef%20Class.md)|Представляет ссылку на объект типа ComPtr \< T>.|  
|[Класс ComPtrRefBase](../windows/comptrrefbase-class.md)|Представляет базовый класс для [ComPtrRef](../Topic/ComPtrRef%20Class.md) класса.|  
|[Класс DontUseNewUseMake](../windows/dontusenewusemake-class.md)|Предотвращает использование оператора `new` в `RuntimeClass`. Следовательно, необходимо использовать [функция](../windows/make-function.md) вместо.|  
|[Класс EventTargetArray](../windows/eventtargetarray-class.md)|Представляет массив обработчики событий.|  
|[Класс MakeAllocator](../windows/makeallocator-class.md)|Выделяет память для активируемого класса, независимо от поддержки слабой ссылки.|  
|[Класс ModuleBase](../windows/modulebase-class.md)|Представляет базовый класс для [модуля](../windows/module-class.md) классы.|  
|[Класс RemoveIUnknown](../windows/removeiunknown-class.md)|Создает тип, эквивалентный `IUnknown`-основе, но имеющий невиртуальные `QueryInterface`, `AddRef`, и `Release` методы.|  
|[Класс WeakReference](../windows/weakreference-class1.md)|Представляет *слабую ссылку* может использоваться с помощью среды выполнения Windows или классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|  
  
### <a name="structures"></a>Структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура ArgTraits](../windows/argtraits-structure.md)|Объявляет указанный делегат интерфейс и анонимную функцию-член, имеющий указанное число параметров.|  
|[Структура ArgTraitsHelper](../windows/argtraitshelper-structure.md)|Помогает определить общие характеристики аргументов делегата.|  
|[Структура BoolStruct](../windows/boolstruct-structure.md)|Определяет, является ли объект ComPtr управление временем существования объектов интерфейса. BoolStruct используется внутри [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) оператор.|  
|[Структура CreatorMap](../windows/creatormap-structure.md)|Содержит сведения об инициализации, регистрации и отмены регистрации объектов.|  
|[Derefhelper-структура](../Topic/DerefHelper%20Structure.md)|Представляет разыменованный указатель на параметр шаблона `T*`.|  
|[Структура EnableIf](../windows/enableif-structure.md)|Определяет данные-член типа, указанного в качестве второго параметра шаблона, если первый параметр шаблона равен `true`.|  
|[Factorycache-структура](../Topic/FactoryCache%20Structure.md)|Содержит местоположение фабрики класса и значение, которое идентифицирует зарегистрированный [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] или COM-объект класса.|  
|[Структура ImplementsBase](../windows/implementsbase-structure.md)|Используется для проверки типов параметров шаблона в [структура реализует](../Topic/Implements%20Structure.md).|  
|[Структура ImplementsHelper](../windows/implementshelper-structure.md)|Помогает реализовать [реализует](../Topic/Implements%20Structure.md) структуры.|  
|[Структура InterfaceList](../windows/interfacelist-structure.md)|Используется для создания рекурсивный список интерфейсов.|  
|[Структура InterfaceListHelper](../Topic/InterfaceListHelper%20Structure.md)|Строит `InterfaceList` типа путем рекурсивного применения аргументов параметра указанного шаблона.|  
|[Структура InterfaceTraits](../windows/interfacetraits-structure.md)|Реализует общие характеристики интерфейса.|  
|[Структура InvokeHelper](../windows/invokehelper-structure.md)|Предоставляет реализацию метода Invoke() на основании указанного числа и типа аргументов.|  
|[Структура IsBaseOfStrict](../windows/isbaseofstrict-structure.md)|Проверяет, является ли один тип базовым для другого.|  
|[Структура IsSame](../windows/issame-structure.md)|Определяет, совпадают ли указанные типы друг с другом.|  
|[Структура nil](../Topic/Nil%20Structure.md)|Используется для указания шаблона неопределенный, необязательный параметр.|  
|[Структура RemoveReference](../windows/removereference-structure.md)|Удаляет ссылку или ссылка rvalue признака из параметра шаблона указанного класса.|  
|[Структура RuntimeClassBase](../windows/runtimeclassbase-structure.md)|Используется для обнаружения `RuntimeClass` в [сделать](../windows/make-function.md) функции.|  
|[Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)|Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.|  
|[Структура VerifyInheritanceHelper](../windows/verifyinheritancehelper-structure.md)|Проверяет, является ли один интерфейс является производным от другого интерфейса.|  
|[Структура VerifyInterfaceHelper](../windows/verifyinterfacehelper-structure.md)|Проверяется соответствие определенным требованиям интерфейс, указанный параметром шаблона.|  
  
### <a name="enumerations"></a>Перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление AsyncStatusInternal](../windows/asyncstatusinternal-enumeration.md)|Задает сопоставление между внутренними перечислениями состояний асинхронных операций и **Windows::Foundation::AsyncStatus** перечисления.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция ActivationFactoryCallback](../windows/activationfactorycallback-function.md)|Получает фабрику активации для активации указанного идентификатора.|  
|[Move-функция](../Topic/Move%20Function.md)|Перемещает указанный аргумент из одного расположения в другое.|  
|[RaiseException-функция](../windows/raiseexception-function.md)|Вызывает исключение в вызывающем потоке.|  
|[Функция Swap (библиотека шаблонов C++ среды выполнения Windows)](../windows/swap-function-windows-runtime-cpp-template-library.md)|Меняет местами значения двух указанных аргументов.|  
|[Функция TerminateMap](../windows/terminatemap-function.md)|Завершает работу фабрик классов в указанном модуле.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Пространство имен Microsoft::wrl:: wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)