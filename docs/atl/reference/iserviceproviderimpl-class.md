---
title: "Класс IServiceProviderImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 69a59fe23b3ca787dee86b1bbdc6775a44903f91
ms.lasthandoff: 02/24/2017

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
|[IServiceProviderImpl::QueryService](#queryservice)|Создает или получает доступ к указанной службе и возвращает указатель интерфейса, заданный интерфейс для службы.|  
  
## <a name="remarks"></a>Примечания  
 `IServiceProvider` Интерфейс определяет службу, указанного по его идентификатору GUID и возвращает указатель на интерфейс для запрошенного интерфейса службы. Класс `IServiceProviderImpl` предоставляет стандартную реализацию этого интерфейса.  
  
 **IServiceProviderImpl** указывает один метод: [QueryService](#queryservice), который создает или получает доступ к указанной службе и возвращает указатель интерфейса, заданный интерфейс для службы.  
  
 `IServiceProviderImpl`использует схему службы, начиная с [BEGIN_SERVICE_MAP](http://msdn.microsoft.com/library/3c6ae156-8776-4588-8227-2d234daec236) и заканчивая [END_SERVICE_MAP](http://msdn.microsoft.com/library/9a35d02a-014c-413a-bb0b-bcca11ab45a6).  
  
 Служба содержит две записи: [SERVICE_ENTRY](http://msdn.microsoft.com/library/e65ff9cc-15e8-41cf-b686-f99eb6686ca9), указывающая идентификатор указанной службы (SID), поддерживаемые объектом, и [SERVICE_ENTRY_CHAIN](http://msdn.microsoft.com/library/09be4ce4-3ccd-4ff2-a95e-a9d5275354c1), какие вызовы `QueryService` цепь к другому объекту.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="queryservice"></a>IServiceProviderImpl::QueryService  
 Создает или получает доступ к указанной службе и возвращает указатель интерфейса, заданный интерфейс для службы.  
  
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
 Возвращаемый `HRESULT` значение является одним из следующих:  
  
|Возвращаемое значение|Значение|  
|------------------|-------------|  
|S_OK|Служба успешно создана или получить.|  
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми.|  
|E_OUTOFMEMORY|Не хватает памяти для создания службы.|  
|E_UNEXPECTED|Произошла неизвестная ошибка.|  
|E_NOINTERFACE|Запрошенный интерфейс не является частью этой службы или службы неизвестно.|  
  
### <a name="remarks"></a>Примечания  
 `QueryService`Возвращает косвенный указатель на запрошенный интерфейс в указанной службе. Вызывающий объект отвечает за освобождение этого указателя, когда он больше не требуется.  
  
 При вызове `QueryService`, передайте идентификатор службы ( `guidService`) и идентификатор интерфейса ( `riid`). `guidService` Указывает службу, для которой требуется доступ, и `riid` определяет интерфейс, который является частью службы. В ответ вы получите косвенный указатель на интерфейс.  
  
 Объект, реализующий интерфейс также может реализовывать интерфейсы, которые являются частью других служб. Рассмотрим следующий пример.  
  
-   Некоторые из этих интерфейсов может быть необязательным. Не все интерфейсы, определенные в описании службы всегда присутствуют в каждой реализации службы или для каждого возвращаемого объекта.  
  
-   В отличие от вызовов `QueryInterface`, передав идентификатор другой службе не обязательно означает, что возвращается другой объект модели компонентных объектов (COM).  
  
-   Возвращенный объект может иметь дополнительные интерфейсы, которые не являются частью определения службы.  
  
 Две разные службы, такие как SID_SMyService и SID_SYourService, оба задается использование один и тот же интерфейс, несмотря на то, что общего между двумя службами будет нечего реализацию интерфейса. Это работает, так как вызов `QueryService` (SID_SMyService, IID_IDispatch) может возвращать объектом, отличным от `QueryService` (SID_SYourService, IID_IDispatch). Удостоверение объекта не предполагается, что при указании идентификатора другую службу.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

