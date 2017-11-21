---
title: "Класс IServiceProviderImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs: C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 39dbab33f631ab9e0dc2b605169e92b6d12d78a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="iserviceproviderimpl-class"></a>Класс IServiceProviderImpl
Этот класс предоставляет реализацию по умолчанию `IServiceProvider` интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IServiceProviderImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IServiceProviderImpl::QueryService](#queryservice)|Создает или получает доступ к указанной службы и возвращает указатель интерфейса на указанный интерфейс для службы.|  
  
## <a name="remarks"></a>Примечания  
 `IServiceProvider` Находит службы, указанной в его идентификатора GUID интерфейса и возвращает указатель на интерфейс для запрошенного интерфейса на стороне службы. Класс `IServiceProviderImpl` предоставляет стандартную реализацию этого интерфейса.  
  
 **IServiceProviderImpl** указывает один из методов: [QueryService](#queryservice), который создает или получает доступ к указанной службы и возвращает указатель интерфейса на указанный интерфейс для службы.  
  
 `IServiceProviderImpl`использует схемы услуг, начиная с [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) и заканчивая [END_SERVICE_MAP](service-map-macros.md#end_service_map).  
  
 Сопоставление службы содержит две записи: [SERVICE_ENTRY](service-map-macros.md#service_entry), указывающая идентификатор указанной службы (SID), поддерживаемые объектом, и [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain), который вызывает `QueryService` цепочку в другой объект.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="queryservice"></a>IServiceProviderImpl::QueryService  
 Создает или получает доступ к указанной службы и возвращает указатель интерфейса на указанный интерфейс для службы.  
  
```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 [IN]`guidService`  
 Указатель на идентификатор службы (SID).  
  
 [IN]`riid`  
 Идентификатор интерфейса, к которому вызывающий объект для получения доступа.  
  
 [OUT]`ppvObj`  
 Косвенный указатель на запрошенный интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращенный `HRESULT` значение является одним из следующих:  
  
|Возвращаемое значение|Значение|  
|------------------|-------------|  
|S_OK|Служба успешно создана или извлечь.|  
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми.|  
|E_OUTOFMEMORY|Не хватает памяти для создания службы.|  
|E_UNEXPECTED|Произошла неизвестная ошибка.|  
|E_NOINTERFACE|Требуемый интерфейс не является частью этой службы или службы неизвестно.|  
  
### <a name="remarks"></a>Примечания  
 `QueryService`Возвращает косвенный указатель на запрошенный интерфейс в указанной службы. Вызывающий объект отвечает за освобождение этого указателя, когда он больше не требуется.  
  
 При вызове `QueryService`, передать идентификатор службы ( `guidService`) и идентификатор интерфейса ( `riid`). `guidService` Указывает службу, к которому вы хотите получить доступ, и `riid` определяет интерфейс, который является частью службы. В ответ будет получен косвенный указатель на интерфейс.  
  
 Объект, реализующий интерфейс также может реализовывать интерфейсы, которые являются частью других служб. Рассмотрим следующий пример.  
  
-   Некоторые из этих интерфейсов может быть необязательным. Не все интерфейсы, определенные в описании службы всегда присутствуют в каждой реализации службы или для каждого возвращаемого объекта.  
  
-   В отличие от вызовов `QueryInterface`, передавая идентификатор другой службе не обязательно означает, возвращается объект различных объектов модели компонентов (COM).  
  
-   Возвращенный объект может иметь дополнительные интерфейсы, которые не являются частью определения службы.  
  
 Две разные службы, такие как SID_SMyService и SID_SYourService, могут обе конечные точки задают использование один и тот же интерфейс, несмотря на то, что реализацию интерфейса может ничего общего между двумя службами. Это работает, так как вызов `QueryService` (SID_SMyService, IID_IDispatch) могут возвращать объектом, отличным от `QueryService` (SID_SYourService, IID_IDispatch). Удостоверение объекта не предполагается, что при указании идентификатора другую службу.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
