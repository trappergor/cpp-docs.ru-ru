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
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: eea45a3315237c77eff0231d485111cefb8557cc
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="service-map-macros"></a>Макросы схемы службы
Эти макросы определить сопоставления служб и операций.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|Отмечает начало ATL службы сопоставления.|  
|[END_SERVICE_MAP](#end_service_map)|Отмечает конец ATL службы сопоставления.|  
|[SERVICE_ENTRY](#service_entry)|Указывает, что объект поддерживает идентификатор конкретной службы.|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Указывает, что [IServiceProviderImpl::QueryService](#queryservice) цепь к указанному объекту.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
   
##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 Отмечает начало схемы услуг.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Указывает класс, содержащий карту службы.  
  
### <a name="remarks"></a>Примечания  
 Сопоставление службы используется для реализации функциональных возможностей поставщика службы на COM-объект. Во-первых, необходимо создать производный класс от [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Существует два типа операций:  
  
- [SERVICE_ENTRY](#service_entry) указывает поддержку для указанного идентификатора (SID) службы.  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) Instructs [IServiceProviderImpl::QueryService](#queryservice) в цепочке в другую, указанного объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#57;](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>END_SERVICE_MAP  
 Отмечает конец схемы услуг.  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry"></a>SERVICE_ENTRY  
 Указывает, что объект поддерживает службы идентификатором, указанным параметром *SID*.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>Параметры  
 *ИД БЕЗОПАСНОСТИ*  
 ИД службы.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 Указывает, что [IServiceProviderImpl::QueryService](#queryservice) в цепочке для объекта, указанного параметром `punk`.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>Параметры  
 `punk`  
 Указатель на **IUnknown** интерфейса, к которому в цепочке.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_SERVICE_MAP](#begin_service_map).  
  
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
 [Макросы](../../atl/reference/atl-macros.md)

