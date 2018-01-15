---
title: "Структура ITopologyExecutionResource | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs: C++
helpviewer_keywords: ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: caf2cc77cd31df611f71d07c5a0a49f600767f81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="itopologyexecutionresource-structure"></a>Структура ITopologyExecutionResource
Интерфейс для ресурса выполнения, как определено диспетчером ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[ITopologyExecutionResource::GetId](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.|  
|[ITopologyExecutionResource::GetNext](#getnext)|Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.|  
  
## <a name="remarks"></a>Примечания  
 Обычно этот интерфейс используется для прохода топологии системы, что наблюдается диспетчером ресурсов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getid"></a>Метод ITopologyExecutionResource::GetId  
 Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.  
  
##  <a name="getnext"></a>Метод ITopologyExecutionResource::GetNext  
 Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс для следующего ресурса выполнения в порядке перечисления. Если больше нет узлов в порядке перечисления узла, которому принадлежит этот ресурс выполнения, этот метод возвращает значение `NULL`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
