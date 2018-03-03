---
title: "Пространство имен Microsoft::wrl:: Details | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f005969908252602cb2fb4bdd73d3b55ae342a99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="microsoftwrldetails-namespace"></a>Пространство имен Microsoft::WRL::Details
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Класс ComPtrRef](../windows/comptrref-class.md)|Представляет ссылку на объект ComPtr типа\<T >.|  
|[Класс ComPtrRefBase](../windows/comptrrefbase-class.md)|Представляет базовый класс для [ComPtrRef](../windows/comptrref-class.md) класса.|  
|[Класс DontUseNewUseMake](../windows/dontusenewusemake-class.md)|Предотвращает использование оператора `new` в `RuntimeClass`. Следовательно, необходимо использовать [функция](../windows/make-function.md) вместо него.|  
|[Класс EventTargetArray](../windows/eventtargetarray-class.md)|Представляет массив дескрипторов событий.|  
|[Класс MakeAllocator](../windows/makeallocator-class.md)|Выделяет память для активируемого класса, независимо от поддержки слабой ссылки.|  
|[Класс ModuleBase](../windows/modulebase-class.md)|Представляет базовый класс для [модуль](../windows/module-class.md) классы.|  
|[Класс RemoveIUnknown](../windows/removeiunknown-class.md)|Создает тип, эквивалентный `IUnknown`-зависимости, но имеющий невиртуальные `QueryInterface`, `AddRef`, и `Release` методы.|  
|[Класс WeakReference](../windows/weakreference-class1.md)|Представляет *слабой ссылки* может использоваться с среды выполнения Windows или классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|  
  
### <a name="structures"></a>Структуры  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Структура ArgTraits](../windows/argtraits-structure.md)|Объявляет указанный делегат интерфейс и анонимную функцию-член, имеющий указанное число параметров.|  
|[Структура ArgTraitsHelper](../windows/argtraitshelper-structure.md)|Помогает определить общие характеристики аргументов делегата.|  
|[Структура BoolStruct](../windows/boolstruct-structure.md)|Определяет, ли объект ComPtr управление временем существования объекта интерфейса. BoolStruct используется внутренним образом [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) оператор.|  
|[Структура CreatorMap](../windows/creatormap-structure.md)|Содержит сведения об инициализации, регистрировать и отменять регистрацию объектов.|  
|[Структура DerefHelper](../windows/derefhelper-structure.md)|Представляет разыменованный указатель на параметр шаблона `T*`.|  
|[Структура EnableIf](../windows/enableif-structure.md)|Определяет данные-член типа, указанного в качестве второго параметра шаблона, если первый параметр шаблона равен `true`.|  
|[Структура FactoryCache](../windows/factorycache-structure.md)|Содержит местоположение фабрики класса и значение, которое идентифицирует зарегистрированный объект среды выполнения Windows или COM-класса.|  
|[Структура ImplementsBase](../windows/implementsbase-structure.md)|Используется для проверки типов параметров шаблона в [структура реализует](../windows/implements-structure.md).|  
|[Структура ImplementsHelper](../windows/implementshelper-structure.md)|Помогает реализовать [реализует](../windows/implements-structure.md) структуры.|  
|[Структура InterfaceList](../windows/interfacelist-structure.md)|Используется для создания рекурсивный список интерфейсов.|  
|[Структура InterfaceListHelper](../windows/interfacelisthelper-structure.md)|Выполняет построение `InterfaceList` тип путем рекурсивного применения аргументов параметра указанного шаблона.|  
|[Структура InterfaceTraits](../windows/interfacetraits-structure.md)|Реализует общие характеристики интерфейса.|  
|[Структура InvokeHelper](../windows/invokehelper-structure.md)|Предоставляет реализацию на основе заданного числа и тип аргументов метода Invoke().|  
|[Структура IsBaseOfStrict](../windows/isbaseofstrict-structure.md)|Проверяет, является ли один тип базовым для другого.|  
|[Структура IsSame](../windows/issame-structure.md)|Определяет, совпадают ли указанные типы друг с другом.|  
|[Структура Nil](../windows/nil-structure.md)|Используется для указания параметра шаблона неопределенный, необязательно.|  
|[Структура RemoveReference](../windows/removereference-structure.md)|Удаляет ссылку или ссылку rvalue признака из параметра шаблона указанного класса.|  
|[Структура RuntimeClassBase](../windows/runtimeclassbase-structure.md)|Позволяет определить `RuntimeClass` в [сделать](../windows/make-function.md) функции.|  
|[Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)|Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.|  
|[Структура VerifyInheritanceHelper](../windows/verifyinheritancehelper-structure.md)|Проверяет, является ли один интерфейс является производным от другого интерфейса.|  
|[Структура VerifyInterfaceHelper](../windows/verifyinterfacehelper-structure.md)|Проверяет, отвечает ли определенным требованиям, что интерфейс, определяемый параметром шаблона.|  
  
### <a name="enumerations"></a>Перечисления  
  
|name|Описание:|  
|----------|-----------------|  
|[Перечисление AsyncStatusInternal](../windows/asyncstatusinternal-enumeration.md)|Задает сопоставление между внутренними перечислениями состояний асинхронных операций и **Windows::Foundation::AsyncStatus** перечисления.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Функция ActivationFactoryCallback](../windows/activationfactorycallback-function.md)|Получает фабрику активации для активации указанного идентификатора.|  
|[Функция Move](../windows/move-function.md)|Перемещает указанный аргумент из одного расположения в другое.|  
|[Функция RaiseException](../windows/raiseexception-function.md)|Вызывает исключение в вызывающем потоке.|  
|[Функция Swap (библиотека шаблонов C++ среды выполнения Windows)](../windows/swap-function-windows-runtime-cpp-template-library.md)|Меняет местами значения двух указанных аргументов.|  
|[Функция TerminateMap](../windows/terminatemap-function.md)|Завершает работу фабрик классов в указанном модуле.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)