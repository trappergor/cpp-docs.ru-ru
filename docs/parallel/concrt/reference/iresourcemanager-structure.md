---
title: "Структура IResourceManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IResourceManager
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: fb523127f60c4e8cd45b2525749b536ad55849b0
ms.lasthandoff: 02/24/2017

---
# <a name="iresourcemanager-structure"></a>Структура IResourceManager
Интерфейс для диспетчера ресурсов среды выполнения с параллелизмом. Это интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IResourceManager;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-enumerations"></a>Открытые перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление IResourceManager::OSVersion](#osversion)|Перечислимый тип, представляющий версию операционной системы.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод IResourceManager::CreateNodeTopology](#createnodetopology)|Присутствует только в отладочной сборки среды выполнения, этот метод является обработчик тестов, разработанный для упрощения тестирования диспетчера ресурсов на различные аппаратные топологии, не требуя аппаратным соответствия конфигурации. С розничными построениями среды выполнения этот метод возвращает не выполняя никаких действий.|  
|[Метод IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Возвращает количество узлов, доступных диспетчеру ресурсов.|  
|[Метод IResourceManager::GetFirstNode](#getfirstnode)|Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.|  
|[Метод IResourceManager::Reference](#reference)|Увеличивает значение счетчика ссылок на экземпляр диспетчера ресурсов.|  
|[Метод IResourceManager::RegisterScheduler](#registerscheduler)|Регистрирует планировщик с диспетчером ресурсов. После регистрации планировщика, его необходимо связаться с диспетчером ресурсов с помощью `ISchedulerProxy` интерфейс, который возвращается.|  
|[Метод IResourceManager::Release](#release)|Уменьшает счетчик ссылок на экземпляр диспетчера ресурсов. Диспетчер ресурсов уничтожается, когда его счетчик ссылок становится равен `0`.|  
  
## <a name="remarks"></a>Примечания  
 Используйте [CreateResourceManager](concurrency-namespace-functions.md) функции для получения интерфейса на экземпляр одноэлементного диспетчера ресурсов. Метод увеличивает значение счетчика ссылок диспетчера ресурсов и необходимо вызвать [IResourceManager::Release](#release) метод, чтобы освободить ссылку, когда выполняются с помощью диспетчера ресурсов. Обычно каждый создаваемый планировщик при создании будет вызывать этот метод во время создания и освободить ссылку для диспетчера ресурсов после завершения работы.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IResourceManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namecreatenodetopologya--iresourcemanagercreatenodetopology-method"></a><a name="createnodetopology"></a>Метод IResourceManager::CreateNodeTopology  
 Присутствует только в отладочной сборки среды выполнения, этот метод является обработчик тестов, разработанный для упрощения тестирования диспетчера ресурсов на различные аппаратные топологии, не требуя аппаратным соответствия конфигурации. С розничными построениями среды выполнения этот метод возвращает не выполняя никаких действий.  
  
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
 [invalid_argument](../../../standard-library/invalid-argument-class.md) создается, если параметр `nodeCount` имеет значение `0` был передан, или если параметр `pCoreCount` имеет значение `NULL`.  
  
 [invalid_operation](invalid-operation-class.md) создается, если этот метод вызывается, когда другие планировщики существует в процессе.  
  
##  <a name="a-namegetavailablenodecounta--iresourcemanagergetavailablenodecount-method"></a><a name="getavailablenodecount"></a>Метод IResourceManager::GetAvailableNodeCount  
 Возвращает количество узлов, доступных диспетчеру ресурсов.  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество узлов, доступных диспетчеру ресурсов.  
  
##  <a name="a-namegetfirstnodea--iresourcemanagergetfirstnode-method"></a><a name="getfirstnode"></a>Метод IResourceManager::GetFirstNode  
 Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый узел в порядке перечисления, определенном диспетчером ресурсов.  
  
##  <a name="a-nameiresourcemanagerosversiona--iresourcemanagerosversion-enumeration"></a><a name="iresourcemanager__osversion"></a>Перечисление IResourceManager::OSVersion  
 Перечислимый тип, представляющий версию операционной системы.  
  
```
enum OSVersion;
```  
  
##  <a name="a-namereferencea--iresourcemanagerreference-method"></a><a name="reference"></a>Метод IResourceManager::Reference  
 Увеличивает значение счетчика ссылок на экземпляр диспетчера ресурсов.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик ссылок.  
  
##  <a name="a-nameregisterschedulera--iresourcemanagerregisterscheduler-method"></a><a name="registerscheduler"></a>Метод IResourceManager::RegisterScheduler  
 Регистрирует планировщик с диспетчером ресурсов. После регистрации планировщика, его необходимо связаться с диспетчером ресурсов с помощью `ISchedulerProxy` интерфейс, который возвращается.  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pScheduler`  
 `IScheduler` Интерфейс для планировщика для регистрации.  
  
 `version`  
 Версия интерфейса связи планировщик используется для взаимодействия с диспетчером ресурсов. Использование версии позволяет диспетчеру ресурсов развивать интерфейс связи, предоставляя планировщикам возможность для получения доступа к старым функциям. Планировщики, которые хотят использовать возможности диспетчера ресурсов в Visual Studio 2010 следует использовать версию `CONCRT_RM_VERSION_1`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `ISchedulerProxy` Интерфейса диспетчера ресурсов связан с данным планировщиком. Планировщику следует использовать этот интерфейс для взаимодействия с диспетчером ресурсов с этого момента на.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно используйте для инициации связи с диспетчером ресурсов. Связывает метод `IScheduler` интерфейс для планировщика с `ISchedulerProxy` интерфейса и его обратно на руках. Возвращенный интерфейс можно использовать для запроса ресурсов выполнения для использования вашим диспетчером или подписать потоки с диспетчером ресурсов. Диспетчер ресурсов будет использовать элементы политики из политики планировщика, возвращенный [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) метод, чтобы определить, какой тип потоков планировщик потребуется для выполнения своей работы. Если ваш `SchedulerKind` ключ политики имеет значение `UmsThreadDefault` и значение считывается обратно из политики как значение `UmsThreadDefault`, `IScheduler` интерфейс, передаваемый в метод должен быть `IUMSScheduler` интерфейса.  
  
 Метод создает `invalid_argument` исключение если параметр `pScheduler` имеет значение `NULL` или, если параметр `version` не является допустимой версией интерфейса взаимодействия.  
  
##  <a name="a-namereleasea--iresourcemanagerrelease-method"></a><a name="release"></a>Метод IResourceManager::Release  
 Уменьшает счетчик ссылок на экземпляр диспетчера ресурсов. Диспетчер ресурсов уничтожается, когда его счетчик ссылок становится равен `0`.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик ссылок.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура ISchedulerProxy](ischedulerproxy-structure.md)   
 [Структура IScheduler](ischeduler-structure.md)

