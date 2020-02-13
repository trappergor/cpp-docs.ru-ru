---
title: Структура IResourceManager
ms.date: 03/27/2019
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
ms.openlocfilehash: 7ce5b07f5eb4272db1b00b7f0105b790ddbb28fe
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142986"
---
# <a name="iresourcemanager-structure"></a>Структура IResourceManager

Интерфейс для диспетчера ресурсов среды выполнения с параллелизмом. Это интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
struct IResourceManager;
```

## <a name="members"></a>Члены

### <a name="public-enumerations"></a>Открытые перечисления

|Имя|Description|
|----------|-----------------|
|[Метод IResourceManager:: OSVersion](#osversion)|Перечислимый тип, представляющий версию операционной системы.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Метод IResourceManager:: Креатенодетопологи](#createnodetopology)|Этот метод предназначен только в отладочных сборках среды выполнения. Это тестовый обработчик, разработанный для упрощения тестирования диспетчер ресурсов в различных аппаратных топологиях без необходимости в фактическом оборудовании, соответствующем конфигурации. При использовании розничных сборок среды выполнения этот метод будет возвращаться без выполнения каких бы то ни было действий.|
|[Метод IResourceManager:: Жетаваилабленодекаунт](#getavailablenodecount)|Возвращает количество узлов, доступных диспетчеру ресурсов.|
|[Метод IResourceManager:: Жетфирстноде](#getfirstnode)|Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.|
|[Метод IResourceManager:: Reference](#reference)|Увеличивает значение счетчика ссылок на экземпляре диспетчер ресурсов.|
|[Метод IResourceManager:: Регистерсчедулер](#registerscheduler)|Регистрирует планировщик с диспетчер ресурсов. После регистрации планировщика он должен взаимодействовать с диспетчер ресурсов с помощью возвращаемого интерфейса `ISchedulerProxy`.|
|[Метод IResourceManager:: Release](#release)|Уменьшает значение счетчика ссылок на экземпляре диспетчер ресурсов. Диспетчер ресурсов уничтожается, когда счетчик ссылок переходит в `0`.|

## <a name="remarks"></a>Remarks

Используйте функцию [креатересаурцеманажер](concurrency-namespace-functions.md) , чтобы получить интерфейс для одноэлементного экземпляра диспетчер ресурсов. Метод увеличивает счетчик ссылок на диспетчер ресурсов, и необходимо вызвать метод [метод IResourceManager:: Release](#release) , чтобы освободить ссылку после завершения диспетчер ресурсов. Как правило, каждый создаваемый планировщик будет вызывать этот метод во время создания и освободить ссылку на диспетчер ресурсов после завершения работы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IResourceManager`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="createnodetopology"></a>Метод метод IResourceManager:: Креатенодетопологи

Этот метод предназначен только в отладочных сборках среды выполнения. Это тестовый обработчик, разработанный для упрощения тестирования диспетчер ресурсов в различных аппаратных топологиях без необходимости в фактическом оборудовании, соответствующем конфигурации. При использовании розничных сборок среды выполнения этот метод будет возвращаться без выполнения каких бы то ни было действий.

```cpp
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Параметры

*nodeCount*<br/>
Число моделируемых узлов процессора.

*пкорекаунт*<br/>
Массив, указывающий количество ядер на каждом узле.

*пнодедистанце*<br/>
Матрица, указывающая расстояние узла между любыми двумя узлами. Этот параметр может иметь значение `NULL`.

*ппроцессорграупс*<br/>
Массив, указывающий группу процессоров, к которой принадлежит каждый узел.

### <a name="remarks"></a>Remarks

[invalid_argument](../../../standard-library/invalid-argument-class.md) возникает, если параметр `nodeCount` имеет значение `0` было передано или если параметр `pCoreCount` имеет значение `NULL`.

[invalid_operation](invalid-operation-class.md) создается, если этот метод вызывается, когда в процессе существуют другие планировщики.

## <a name="getavailablenodecount"></a>Метод метод IResourceManager:: Жетаваилабленодекаунт

Возвращает количество узлов, доступных диспетчеру ресурсов.

```cpp
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество узлов, доступных для диспетчер ресурсов.

## <a name="getfirstnode"></a>Метод метод IResourceManager:: Жетфирстноде

Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.

```cpp
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Первый узел в порядке перечисления, определенный диспетчер ресурсов.

## <a name="osversion"></a>Перечисление метод IResourceManager:: OSVersion

Перечислимый тип, представляющий версию операционной системы.

```cpp
enum OSVersion;
```

## <a name="reference"></a>Метод метод IResourceManager:: Reference

Увеличивает значение счетчика ссылок на экземпляре диспетчер ресурсов.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Результирующий счетчик ссылок.

## <a name="registerscheduler"></a>Метод метод IResourceManager:: Регистерсчедулер

Регистрирует планировщик с диспетчер ресурсов. После регистрации планировщика он должен взаимодействовать с диспетчер ресурсов с помощью возвращаемого интерфейса `ISchedulerProxy`.

```cpp
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Параметры

*псчедулер*<br/>
Интерфейс `IScheduler` для регистрируемого планировщика.

*version*<br/>
Версия интерфейса связи, используемая планировщиком для взаимодействия с диспетчер ресурсов. Использование версии позволяет диспетчер ресурсов развивать интерфейс связи, одновременно позволяя планировщикам получать доступ к старым функциям. Планировщики, которые хотят использовать диспетчер ресурсов функции, представленные в Visual Studio 2010, должны использовать версию `CONCRT_RM_VERSION_1`.

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `ISchedulerProxy`, который диспетчер ресурсов связан с планировщиком. Ваш планировщик должен использовать этот интерфейс для взаимодействия с диспетчер ресурсов с этого момента.

### <a name="remarks"></a>Remarks

Используйте этот метод, чтобы инициировать связь с диспетчер ресурсов. Метод связывает интерфейс `IScheduler` планировщика с интерфейсом `ISchedulerProxy` и передает его вам. Полученный интерфейс можно использовать для запроса ресурсов выполнения для использования планировщиком или для подписки потоков с диспетчер ресурсов. Диспетчер ресурсов будет использовать элементы политики из политики планировщика, возвращаемой методом [IScheduler:: Policy](ischeduler-structure.md#getpolicy) , чтобы определить, какой тип потоков должен выполнять планировщик. Если ключ политики `SchedulerKind` имеет значение `UmsThreadDefault` и значение считывается из политики в качестве значения `UmsThreadDefault`, то интерфейс `IScheduler`, переданный в метод, должен быть интерфейсом `IUMSScheduler`.

Метод вызывает исключение `invalid_argument`, если параметр `pScheduler` имеет значение `NULL` или если параметр `version` не является допустимой версией для интерфейса связи.

## <a name="release"></a>Метод метод IResourceManager:: Release

Уменьшает значение счетчика ссылок на экземпляре диспетчер ресурсов. Диспетчер ресурсов уничтожается, когда счетчик ссылок переходит в `0`.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Результирующий счетчик ссылок.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура ISchedulerProxy](ischedulerproxy-structure.md)<br/>
[Структура IScheduler](ischeduler-structure.md)
