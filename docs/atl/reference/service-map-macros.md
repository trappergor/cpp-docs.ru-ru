---
title: "Макросы схемы службы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 444d89833d84f23099ff0de8bce29bfc9d0a1344
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="service-map-macros"></a>Макросы схемы службы
Эти макросы определяют схем услуг и записи.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|Отмечает начало карты ATL службы.|  
|[END_SERVICE_MAP](#end_service_map)|Отмечает конец ATL схемы услуг.|  
|[SERVICE_ENTRY](#service_entry)|Указывает, что объект поддерживает с идентификатором конкретной службы.|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Указывает, что [IServiceProviderImpl::QueryService](#queryservice) цепочку в указанный объект.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
   
##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 Отмечает начало карты службы.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Указывает класс, содержащий схему услуг.  
  
### <a name="remarks"></a>Примечания  
 Сопоставление службы используется для реализации функций поставщика службы на COM-объект. Во-первых, необходимо создать производный класс от [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Существует два типа операций:  
  
- [SERVICE_ENTRY](#service_entry) указывает поддержку для указанного ИД службы.  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) Instructs [IServiceProviderImpl::QueryService](#queryservice) цепь на другой, указанный объект.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>END_SERVICE_MAP  
 Отмечает конец схемы услуг.  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry"></a>SERVICE_ENTRY  
 Указывает, что объект поддерживает службы идентификатором, указанным параметром *SID*.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>Параметры  
 *ИД БЕЗОПАСНОСТИ*  
 ИД службы.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 Указывает, что [IServiceProviderImpl::QueryService](#queryservice) в цепочке для объекта, указанного параметром `punk`.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>Параметры  
 `punk`  
 Указатель на **IUnknown** интерфейса, к которому в цепочке.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_SERVICE_MAP](#begin_service_map).  
  
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
 [Макросы](../../atl/reference/atl-macros.md)
