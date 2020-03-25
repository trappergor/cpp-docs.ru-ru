---
title: Пространство имен Microsoft::WRL::Details
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: 4e8d2e5a2c7e6655674c4e965cd7222d930dff9a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213789"
---
# <a name="microsoftwrldetails-namespace"></a>Пространство имен Microsoft::WRL::Details

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>Члены

### <a name="classes"></a>Классы

|Имя|Description|
|----------|-----------------|
|[Класс ComPtrRef](comptrref-class.md)|Представляет ссылку на объект типа ComPtr\<T >.|
|[Класс ComPtrRefBase](comptrrefbase-class.md)|Представляет базовый класс для класса [ComPtrRef](comptrref-class.md) .|
|[Класс DontUseNewUseMake](dontusenewusemake-class.md)|Предотвращает использование оператора `new` в `RuntimeClass`. Следовательно, вместо этого следует использовать [функцию make](make-function.md) .|
|[Класс EventTargetArray](eventtargetarray-class.md)|Представляет массив обработчиков событий.|
|[Класс MakeAllocator](makeallocator-class.md)|Выделяет память для класса активируемого с поддержкой слабых ссылок или без нее.|
|[Класс ModuleBase](modulebase-class.md)|Представляет базовый класс для классов [модулей](module-class.md) .|
|[Класс RemoveIUnknown](removeiunknown-class.md)|Делает тип, эквивалентный типу `IUnknown`, но содержит методы, не являющиеся виртуальными `QueryInterface`, `AddRef`и `Release`.|
|[Класс WeakReference](weakreference-class.md)|Представляет *слабую ссылку* , которую можно использовать с среда выполнения Windows или классическим com. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|

### <a name="structures"></a>Структуры

|Имя|Description|
|----------|-----------------|
|[Структура ArgTraits](argtraits-structure.md)|Объявляет указанный интерфейс делегата и анонимную функцию-член с заданным числом параметров.|
|[Структура ArgTraitsHelper](argtraitshelper-structure.md)|Помогает определить общие характеристики аргументов делегата.|
|[Структура BoolStruct](boolstruct-structure.md)|Определяет, управляет ли `ComPtr` время существования объекта в интерфейсе. `BoolStruct` внутренне используется оператором [BoolType ()](comptr-class.md#operator-microsoft-wrl-details-booltype) .|
|[Структура CreatorMap](creatormap-structure.md)|Содержит сведения о том, как выполнять инициализацию, регистрацию и отмену регистрации объектов.|
|[Структура DerefHelper](derefhelper-structure.md)|Представляет разыменованный указатель на параметр шаблона `T*`.|
|[Структура EnableIf](enableif-structure.md)|Определяет данные-член типа, указанного в качестве второго параметра шаблона, если первый параметр шаблона равен `true`.|
|[Структура FactoryCache](factorycache-structure.md)|Содержит расположение фабрики класса и значение, идентифицирующее зарегистрированный среда выполнения Windows или объект класса COM.|
|[Структура ImplementsBase](implementsbase-structure.md)|Используется для проверки типов параметров шаблона в [структуре Implements](implements-structure.md).|
|[Структура ImplementsHelper](implementshelper-structure.md)|Помогает реализовать структуру [Implements](implements-structure.md) .|
|[Структура InterfaceList](interfacelist-structure.md)|Используется для создания рекурсивного списка интерфейсов.|
|[Структура InterfaceListHelper](interfacelisthelper-structure.md)|Создает тип `InterfaceList`, рекурсивно применяя заданные аргументы параметра шаблона.|
|[Структура InterfaceTraits](interfacetraits-structure.md)|Реализует общие характеристики интерфейса.|
|[Структура InvokeHelper](invokehelper-structure.md)|Предоставляет реализацию метода `Invoke()` на основе указанного числа и типа аргументов.|
|[Структура IsBaseOfStrict](isbaseofstrict-structure.md)|Проверяет, является ли один тип базовым для другого.|
|[Структура IsSame](issame-structure.md)|Определяет, совпадают ли указанные типы друг с другом.|
|[Структура Nil](nil-structure.md)|Используется для указания неуказанного необязательного параметра шаблона.|
|[Структура RemoveReference](removereference-structure.md)|Отделяет ссылку или признак rvalue-reference от указанного параметра шаблона класса.|
|[Структура RuntimeClassBase](runtimeclassbase-structure.md)|Используется для обнаружения `RuntimeClass` в функции [make](make-function.md) .|
|[Структура RuntimeClassBaseT](runtimeclassbaset-structure.md)|Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.|
|[Структура VerifyInheritanceHelper](verifyinheritancehelper-structure.md)|Проверяет, является ли один интерфейс производным от другого интерфейса.|
|[Структура VerifyInterfaceHelper](verifyinterfacehelper-structure.md)|Проверяет, соответствует ли интерфейс, указанный параметром шаблона, определенным требованиям.|

### <a name="enumerations"></a>Перечисления

|Имя|Description|
|----------|-----------------|
|[Перечисление AsyncStatusInternal](asyncstatusinternal-enumeration.md)|Задает сопоставление между внутренними перечислениями состояний асинхронных операций и перечислением `Windows::Foundation::AsyncStatus`.|

### <a name="functions"></a>Функции

|Имя|Description|
|----------|-----------------|
|[Функция ActivationFactoryCallback](activationfactorycallback-function.md)|Возвращает фабрику активации для указанного идентификатора активации.|
|[Функция Move](move-function.md)|Перемещает указанный аргумент из одного расположения в другое.|
|[Функция RaiseException](raiseexception-function.md)|Вызывает исключение в вызывающем потоке.|
|[Функция Swap (WRL)](swap-function-wrl.md)|Меняет местами значения двух указанных аргументов.|
|[Функция TerminateMap](terminatemap-function.md)|Завершает работу фабрик классов в указанном модуле.|

## <a name="requirements"></a>Требования

**Заголовок:** Async. h, Client. h, кореврапперс. h, Event. h, FTM. h, реализует. h, internal. h, Module. h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)<br/>
[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)
