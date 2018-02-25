---
title: "Структура IResourceManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d309e057a8f829b11cc97ad60f3f5d56ff7ecaff
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="iresourcemanager-structure"></a>Структура IResourceManager
Интерфейс для диспетчера ресурсов среды выполнения с параллелизмом. Это интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IResourceManager;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-enumerations"></a>Открытые перечисления  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IResourceManager::OSVersion](#osversion)|Перечислимый тип, представляющий версию операционной системы.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IResourceManager::CreateNodeTopology](#createnodetopology)|Присутствует только в отладочной сборки среды выполнения, этот метод является тестового обработчика, разработанный для упрощения тестирования диспетчера ресурсов на различные аппаратные топологии без необходимости фактического оборудования, соответствующего конфигурации. Этот метод возвращает с коммерческие сборки среды выполнения, не выполняя никаких действий.|  
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Возвращает количество узлов, доступных диспетчеру ресурсов.|  
|[IResourceManager::GetFirstNode](#getfirstnode)|Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.|  
|[IResourceManager::Reference](#reference)|Увеличивает значение счетчика ссылок на экземпляр диспетчера ресурсов.|  
|[IResourceManager::RegisterScheduler](#registerscheduler)|Регистрирует диспетчером ресурсов планировщику. После регистрации планировщика, его необходимо связаться с диспетчером ресурсов с помощью `ISchedulerProxy` интерфейс, который возвращается.|  
|[IResourceManager::Release](#release)|Уменьшает счетчик ссылок на экземпляр диспетчера ресурсов. Диспетчер ресурсов уничтожается, когда число ссылок становится равен `0`.|  
  
## <a name="remarks"></a>Примечания  
 Используйте [CreateResourceManager](concurrency-namespace-functions.md) функцию для получения интерфейса одноэлементный экземпляр диспетчера ресурсов. Метод увеличивает значение счетчика ссылок на диспетчере ресурсов и необходимо вызвать [IResourceManager::Release](#release) метод, чтобы освободить ссылку, когда выполняются с помощью диспетчера ресурсов. Как правило каждый планировщик, создаваемые вами будет этот метод вызывается во время создания и освободить ссылку для диспетчера ресурсов после завершения работы.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IResourceManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="createnodetopology"></a>  IResourceManager::CreateNodeTopology Method  
 Присутствует только в отладочной сборки среды выполнения, этот метод является тестового обработчика, разработанный для упрощения тестирования диспетчера ресурсов на различные аппаратные топологии без необходимости фактического оборудования, соответствующего конфигурации. Этот метод возвращает с коммерческие сборки среды выполнения, не выполняя никаких действий.  
  
```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `nodeCount`  
 Число симулируемых узлов процессора.  
  
 `pCoreCount`  
 Массив, который определяет число ядер на каждом узле.  
  
 `pNodeDistance`  
 Матрица, указывающая узловое расстояние между любыми двумя узлами. Этот параметр может иметь значение `NULL`.  
  
 `pProcessorGroups`  
 Массив, который определяет группу процессора, к которой принадлежит каждый узел.  
  
### <a name="remarks"></a>Примечания  
 [invalid_argument](../../../standard-library/invalid-argument-class.md) создается, если параметр `nodeCount` имеет значение `0` был передан, или, если параметр `pCoreCount` имеет значение `NULL`.  
  
 [invalid_operation](invalid-operation-class.md) создается, если этот метод вызывается, когда другие планировщики существует в процессе.  
  
##  <a name="getavailablenodecount"></a>  Метод IResourceManager::GetAvailableNodeCount  
 Возвращает количество узлов, доступных диспетчеру ресурсов.  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество узлов, доступных диспетчеру ресурсов.  
  
##  <a name="getfirstnode"></a>  IResourceManager::GetFirstNode Method  
 Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый узел в порядке перечисления, определенном диспетчером ресурсов.  
  
##  <a name="iresourcemanager__osversion"></a>  IResourceManager::OSVersion Enumeration  
 Перечислимый тип, представляющий версию операционной системы.  
  
```
enum OSVersion;
```  
  
##  <a name="reference"></a>  Метод IResourceManager::Reference  
 Увеличивает значение счетчика ссылок на экземпляр диспетчера ресурсов.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик ссылок.  
  
##  <a name="registerscheduler"></a>  Метод IResourceManager::RegisterScheduler  
 Регистрирует диспетчером ресурсов планировщику. После регистрации планировщика, его необходимо связаться с диспетчером ресурсов с помощью `ISchedulerProxy` интерфейс, который возвращается.  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pScheduler`  
 `IScheduler` Интерфейс для планировщика для регистрации.  
  
 `version`  
 Версия интерфейса связи использует планировщик для взаимодействия с диспетчером ресурсов. Использование версии позволяет диспетчеру ресурсов развивать интерфейс связи, предоставляя планировщикам для получения доступа к старым функциям. Планировщики, которые хотите использовать возможности диспетчера ресурсов в Visual Studio 2010 следует использовать версию `CONCRT_RM_VERSION_1`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `ISchedulerProxy` Интерфейс диспетчера ресурсов связанный с данным планировщиком. Планировщику следует использовать этот интерфейс для взаимодействия с диспетчером ресурсов с этого момента на.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы установить связь с диспетчером ресурсов. Связывает метод `IScheduler` интерфейс для планировщика с `ISchedulerProxy` интерфейса и его обратно вам руки. Возвращенный интерфейс можно использовать для запроса ресурсов выполнения для использования вашим диспетчером или подписать потоки с диспетчером ресурсов. Диспетчер ресурсов будет использовать элементы политики из политики планировщика, возвращенных [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) метод, чтобы определить, какой тип потоки планировщика потребуется для выполнения своей работы. Если ваш `SchedulerKind` политики ключ имеет значение `UmsThreadDefault` и значение считывается обратно из политики как значение `UmsThreadDefault`, `IScheduler` интерфейс, передаваемый в метод должен быть `IUMSScheduler` интерфейса.  
  
 Метод создает `invalid_argument` исключения Если параметр `pScheduler` имеет значение `NULL` или, если параметр `version` не является допустимой версией интерфейс связи.  
  
##  <a name="release"></a>  Метод IResourceManager::Release  
 Уменьшает счетчик ссылок на экземпляр диспетчера ресурсов. Диспетчер ресурсов уничтожается, когда число ссылок становится равен `0`.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик ссылок.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура ISchedulerProxy](ischedulerproxy-structure.md)   
 [Структура IScheduler](ischeduler-structure.md)
