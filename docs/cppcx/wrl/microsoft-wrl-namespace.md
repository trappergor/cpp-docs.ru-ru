---
title: Пространство имен Microsoft::WRL
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL
- module/Microsoft::WRL
- async/Microsoft::WRL
- internal/Microsoft::WRL
- event/Microsoft::WRL
- ftm/Microsoft::WRL
- client/Microsoft::WRL
- corewrappers/Microsoft::WRL
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
ms.openlocfilehash: 749469c7ae2acf3a0da92d24a51bbfca9b68971d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033525"
---
# <a name="microsoftwrl-namespace"></a>Пространство имен Microsoft::WRL

Определяет основные типы, составляющие библиотека шаблонов C++ среды выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL;
```

## <a name="members"></a>Участники

### <a name="typedefs"></a>Определения типов

|name|Описание|
|----------|-----------------|
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt | InhibitWeakReference>`|

### <a name="classes"></a>Классы

|name|Описание|
|----------|-----------------|
|[ActivationFactory - класс](activationfactory-class.md)|Позволяет одному или нескольким классам быть активированными средой выполнения Windows.|
|[AsyncBase - класс](asyncbase-class.md)|Реализует асинхронный конечный автомат среды выполнения Windows.|
|[ClassFactory - класс](classfactory-class.md)|Реализует базовую функциональность интерфейса `IClassFactory`.|
|[Класс ComPtr](comptr-class.md)|Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. ComPtr автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.|
|[Класс DeferrableEventArgs](deferrableeventargs-class.md)|Класс шаблона, используемый для типов аргументов событий для задержек.|
|[EventSource - класс](eventsource-class.md)|Представляет событие. `EventSource` функции-члены, добавлять, удалять и вызывать обработчики событий.|
|[FtmBase - класс](ftmbase-class.md)|Представляет свободнопоточный объект маршаллера.|
|[Module - класс](module-class.md)|Представляет коллекцию связанных объектов.|
|[Класс RuntimeClass](runtimeclass-class.md)|Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.|
|[SimpleActivationFactory - класс](simpleactivationfactory-class.md)|Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.|
|[SimpleClassFactory - класс](simpleclassfactory-class.md)|Предоставляет основной механизм для создания базового класса.|
|[Класс WeakRef](weakref-class.md)|Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|

### <a name="structures"></a>Структуры

|name|Описание|
|----------|-----------------|
|[ChainInterfaces - структура](chaininterfaces-structure.md)|Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.|
|[CloakedIid - структура](cloakediid-structure.md)|Указывает `RuntimeClass`, `Implements` и `ChainInterfaces` шаблоны, что заданный интерфейс недоступен в списке IID.|
|[Implements - структура](implements-structure.md)|Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.|
|[MixIn - структура](mixin-structure.md)|Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.|
|[RuntimeClassFlags - структура](runtimeclassflags-structure.md)|Содержит тип для экземпляра [RuntimeClass](runtimeclass-class.md).|

### <a name="enumerations"></a>Перечисления

|name|Описание|
|----------|-----------------|
|[AsyncResultType - перечисление](asyncresulttype-enumeration.md)|Указывает тип результата, возвращенный `GetResults()` метод.|
|[ModuleType - перечисление](moduletype-enumeration.md)|Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.|
|[RuntimeClassType - перечисление](runtimeclasstype-enumeration.md)|Указывает тип [RuntimeClass](runtimeclass-class.md) экземпляр, который поддерживается.|

### <a name="functions"></a>Функции

|name|Описание|
|----------|-----------------|
|[AsWeak - функция](asweak-function.md)|Извлекает слабую ссылку на определенный экземпляр.|
|[Функция обратного вызова (WRL)](callback-function-wrl.md)|Создает объект, функция-член которого является методом обратного вызова.|
|[CreateActivationFactory - функция](createactivationfactory-function.md)|Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.|
|[CreateClassFactory - функция](createclassfactory-function.md)|Создает фабрику, которая создает экземпляры указанного класса.|
|[Функция Make](make-function.md)|Инициализирует указанный класс среды выполнения Windows.|

## <a name="requirements"></a>Требования

**Заголовок:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)