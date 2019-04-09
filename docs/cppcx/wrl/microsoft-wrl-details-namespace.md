---
title: Пространство имен Microsoft::WRL::Details
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: fce6e620600164e73d3708d98d8a7fa979e8ab42
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027486"
---
# <a name="microsoftwrldetails-namespace"></a>Пространство имен Microsoft::WRL::Details

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>Участники

### <a name="classes"></a>Классы

|name|Описание|
|----------|-----------------|
|[ComPtrRef - класс](comptrref-class.md)|Представляет ссылку на объект ComPtr типа\<T >.|
|[ComPtrRefBase - класс](comptrrefbase-class.md)|Представляет базовый класс для [ComPtrRef](comptrref-class.md) класса.|
|[DontUseNewUseMake - класс](dontusenewusemake-class.md)|Предотвращает использование оператора `new` в `RuntimeClass`. Следовательно, необходимо использовать [функция](make-function.md) вместо этого.|
|[Класс EventTargetArray](eventtargetarray-class.md)|Представляет собой массив обработчики событий.|
|[MakeAllocator - класс](makeallocator-class.md)|Выделяет память для активируемого класса, с или без поддержку слабых ссылок.|
|[Класс ModuleBase](modulebase-class.md)|Представляет базовый класс для [модуль](module-class.md) классы.|
|[Класс RemoveIUnknown](removeiunknown-class.md)|Создает тип, который эквивалентен `IUnknown`-на основе типа, но имеет невиртуальный `QueryInterface`, `AddRef`, и `Release` методы.|
|[Класс WeakReference](weakreference-class.md)|Представляет *слабую ссылку* , можно использовать с помощью среды выполнения Windows или классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|

### <a name="structures"></a>Структуры

|name|Описание|
|----------|-----------------|
|[ArgTraits - структура](argtraits-structure.md)|Объявляет указанный делегат, интерфейс и анонимную функцию-член, имеющий указанное число параметров.|
|[ArgTraitsHelper - структура](argtraitshelper-structure.md)|Помогает определить общие характеристики аргументов делегата.|
|[BoolStruct - структура](boolstruct-structure.md)|Определяет ли `ComPtr` управление временем существования объектов интерфейса. `BoolStruct` используется внутренним образом [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) оператор.|
|[CreatorMap - структура](creatormap-structure.md)|Содержит сведения о том, как инициализировать, регистрации и отмены регистрации объектов.|
|[DerefHelper - структура](derefhelper-structure.md)|Представляет разыменованный указатель на параметр шаблона `T*`.|
|[EnableIf - структура](enableif-structure.md)|Определяет данные-член типа, указанного в качестве второго параметра шаблона, если первый параметр шаблона равен `true`.|
|[FactoryCache - структура](factorycache-structure.md)|Содержит местоположение фабрики класса и значение, которое идентифицирует зарегистрированный объект среды выполнения Windows или COM-класса.|
|[ImplementsBase - структура](implementsbase-structure.md)|Используется для проверки типов параметров шаблона в [Implements-структура](implements-structure.md).|
|[ImplementsHelper - структура](implementshelper-structure.md)|Помогает реализовать [реализует](implements-structure.md) структуры.|
|[InterfaceList - структура](interfacelist-structure.md)|Используется для создания рекурсивный список интерфейсов.|
|[InterfaceListHelper - структура](interfacelisthelper-structure.md)|Строит `InterfaceList` типа путем рекурсивного применения аргументов параметра указанного шаблона.|
|[InterfaceTraits - структура](interfacetraits-structure.md)|Реализует общие характеристики интерфейса.|
|[InvokeHelper - структура](invokehelper-structure.md)|Предоставляет реализацию `Invoke()` метод на основе заданного числа и типа аргументов.|
|[IsBaseOfStrict - структура](isbaseofstrict-structure.md)|Проверяет, является ли один тип базовым для другого.|
|[IsSame - структура](issame-structure.md)|Определяет, совпадают ли указанные типы друг с другом.|
|[Структура Nil](nil-structure.md)|Используется для указания параметра-шаблона неопределенный, необязательно.|
|[RemoveReference - структура](removereference-structure.md)|Удаляет ссылка или rvalue признака из параметра шаблона указанного класса.|
|[Структура RuntimeClassBase](runtimeclassbase-structure.md)|Позволяет определить `RuntimeClass` в [сделать](make-function.md) функции.|
|[Структура RuntimeClassBaseT](runtimeclassbaset-structure.md)|Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.|
|[VerifyInheritanceHelper - структура](verifyinheritancehelper-structure.md)|Проверяет, является ли один интерфейс является производным от другого интерфейса.|
|[VerifyInterfaceHelper - структура](verifyinterfacehelper-structure.md)|Проверяет, что интерфейс, указанный в параметре шаблона соответствует определенным требованиям.|

### <a name="enumerations"></a>Перечисления

|name|Описание|
|----------|-----------------|
|[AsyncStatusInternal - перечисление](asyncstatusinternal-enumeration.md)|Задает сопоставление между внутренними перечислениями состояний асинхронных операций и перечислением `Windows::Foundation::AsyncStatus`.|

### <a name="functions"></a>Функции

|name|Описание|
|----------|-----------------|
|[ActivationFactoryCallback - функция](activationfactorycallback-function.md)|Возвращает фабрику активации для активации указанного идентификатора.|
|[Move - функция](move-function.md)|Перемещает указанный аргумент из одного расположения в другое.|
|[RaiseException - функция](raiseexception-function.md)|Вызывает исключение в вызывающем потоке.|
|[Функция Swap (WRL)](swap-function-wrl.md)|Меняет местами значения двух заданных аргументов.|
|[Функция TerminateMap](terminatemap-function.md)|Завершает работу фабрик классов в указанном модуле.|

## <a name="requirements"></a>Требования

**Заголовок:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)<br/>
[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)