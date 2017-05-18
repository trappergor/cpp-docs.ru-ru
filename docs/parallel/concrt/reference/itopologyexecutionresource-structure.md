---
title: "Структура ITopologyExecutionResource | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d9671dbf84a1104bc3b6f3a6f9d383aac167759c
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="itopologyexecutionresource-structure"></a>Структура ITopologyExecutionResource
Интерфейс для ресурса выполнения, как определено диспетчером ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[ITopologyExecutionResource::GetId](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.|  
|[ITopologyExecutionResource::GetNext](#getnext)|Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.|  
  
## <a name="remarks"></a>Примечания  
 Обычно этот интерфейс используется для обхода топологии системы соблюдения диспетчером ресурсов.  
  
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

