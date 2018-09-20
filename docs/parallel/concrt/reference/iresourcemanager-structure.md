---
title: Структура IResourceManager | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26181c12bd3775a4fee0086be8459251ddf25afd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413670"
---
# <a name="iresourcemanager-structure"></a>Структура IResourceManager

Интерфейс для диспетчера ресурсов среды выполнения с параллелизмом. Это интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов.

## <a name="syntax"></a>Синтаксис

```
struct IResourceManager;
```

## <a name="members"></a>Участники

### <a name="public-enumerations"></a>Открытые перечисления

|Имя|Описание|
|----------|-----------------|
|[IResourceManager::OSVersion](#osversion)|Перечислимый тип, представляющий версию операционной системы.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IResourceManager::CreateNodeTopology](#createnodetopology)|Присутствует только в отладочной сборки среды выполнения, этот метод является тестового обработчика, разработанный для упрощения тестирования диспетчера ресурсов на различных топологий оборудования, без необходимости фактическое оборудования, соответствующего конфигурации. С помощью розничных сборках среды выполнения этот метод возвращает не выполняя никаких действий.|
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Возвращает количество узлов, доступных диспетчеру ресурсов.|
|[IResourceManager::GetFirstNode](#getfirstnode)|Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.|
|[IResourceManager::Reference](#reference)|Увеличивает счетчик ссылок на экземпляр диспетчера ресурсов.|
|[IResourceManager::RegisterScheduler](#registerscheduler)|Регистрирует планировщик с помощью Resource Manager. После регистрации планировщик, его необходимо связаться с Resource Manager с помощью `ISchedulerProxy` интерфейс, который возвращается.|
|[IResourceManager::Release](#release)|Уменьшает счетчик ссылок на экземпляр диспетчера ресурсов. Диспетчер ресурсов уничтожается в том случае, когда его счетчик ссылок становится равен `0`.|

## <a name="remarks"></a>Примечания

Используйте [CreateResourceManager](concurrency-namespace-functions.md) функцию для получения интерфейса одноэлементный экземпляр диспетчера ресурсов. Метод увеличивает счетчик ссылок с помощью Resource Manager, и необходимо вызвать [IResourceManager::Release](#release) метод для освобождения ссылки, когда вы закончите с помощью Resource Manager. Как правило каждый планировщик, создаваемых будет вызывать этот метод во время создания и освобождение ссылки для диспетчера ресурсов после завершения работы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IResourceManager`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="createnodetopology"></a>  Метод IResourceManager::CreateNodeTopology

Присутствует только в отладочной сборки среды выполнения, этот метод является тестового обработчика, разработанный для упрощения тестирования диспетчера ресурсов на различных топологий оборудования, без необходимости фактическое оборудования, соответствующего конфигурации. С помощью розничных сборках среды выполнения этот метод возвращает не выполняя никаких действий.

```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Параметры

*nodeCount*<br/>
Число симулируемых узлов процессора.

*pCoreCount*<br/>
Массив, который определяет число ядер на каждом узле.

*pNodeDistance*<br/>
Матрица, задающее расстояние узел между любыми двумя узлами. Этот параметр может иметь значение `NULL`.

*pProcessorGroups*<br/>
Массив, который определяет группу процессора, к которой принадлежит каждый узел.

### <a name="remarks"></a>Примечания

[invalid_argument](../../../standard-library/invalid-argument-class.md) возникает, если параметр `nodeCount` имеет значение `0` был передан в, или, если параметр `pCoreCount` имеет значение `NULL`.

[invalid_operation](invalid-operation-class.md) возникает, если этот метод вызывается, когда другие планировщики существует в процессе.

##  <a name="getavailablenodecount"></a>  Метод IResourceManager::GetAvailableNodeCount

Возвращает количество узлов, доступных диспетчеру ресурсов.

```
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество узлов, доступных диспетчеру ресурсов.

##  <a name="getfirstnode"></a>  Метод IResourceManager::GetFirstNode

Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.

```
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Первый узел в порядке перечисления, как определено диспетчером ресурсов.

##  <a name="iresourcemanager__osversion"></a>  Перечисление IResourceManager::OSVersion

Перечислимый тип, представляющий версию операционной системы.

```
enum OSVersion;
```

##  <a name="reference"></a>  Метод IResourceManager::Reference

Увеличивает счетчик ссылок на экземпляр диспетчера ресурсов.

```
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Итоговый счетчик ссылок.

##  <a name="registerscheduler"></a>  Метод IResourceManager::RegisterScheduler

Регистрирует планировщик с помощью Resource Manager. После регистрации планировщик, его необходимо связаться с Resource Manager с помощью `ISchedulerProxy` интерфейс, который возвращается.

```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Параметры

*pScheduler*<br/>
`IScheduler` Интерфейс для планировщика для регистрации.

*version*<br/>
Версия интерфейса взаимодействия использует планировщик для взаимодействия с диспетчером ресурсов. С помощью версии позволяет диспетчеру ресурсов развивать интерфейс связи, предоставляя планировщикам получить доступ к старым функциям. Планировщики, которые хотите использовать возможности диспетчера ресурсов в Visual Studio 2010 следует использовать версию `CONCRT_RM_VERSION_1`.

### <a name="return-value"></a>Возвращаемое значение

`ISchedulerProxy` Интерфейс, связанную с вашей планировщик Resource Manager. Планировщику следует использовать этот интерфейс для взаимодействия с помощью Resource Manager с этого момента по.

### <a name="remarks"></a>Примечания

Этот метод позволяет инициировать соединение с диспетчером ресурсов. Связывает метод `IScheduler` интерфейс для планировщика с `ISchedulerProxy` интерфейса и передает его обратно вам. Возвращенный интерфейс можно использовать для запроса ресурсов выполнения для использования вашим диспетчером или подписать потоки с диспетчером ресурсов. Диспетчер ресурсов будет использовать элементы политики из политики планировщика, возвращенный [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) метод, чтобы определить, какой тип потоков планировщик потребуются для выполнения работы. Если ваш `SchedulerKind` ключ политики имеет значение `UmsThreadDefault` и значение считывается обратно из политики, как значение `UmsThreadDefault`, `IScheduler` интерфейс, передается в метод должен быть `IUMSScheduler` интерфейс.

Метод вызывает `invalid_argument` исключения Если параметр `pScheduler` имеет значение `NULL` или, если параметр `version` не является допустимой версией для интерфейса взаимодействия.

##  <a name="release"></a>  Метод IResourceManager::Release

Уменьшает счетчик ссылок на экземпляр диспетчера ресурсов. Диспетчер ресурсов уничтожается в том случае, когда его счетчик ссылок становится равен `0`.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Итоговый счетчик ссылок.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура ISchedulerProxy](ischedulerproxy-structure.md)<br/>
[Структура IScheduler](ischeduler-structure.md)
