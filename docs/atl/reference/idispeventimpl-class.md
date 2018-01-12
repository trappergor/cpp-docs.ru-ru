---
title: "Класс IDispEventImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
dev_langs: C++
helpviewer_keywords: IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f052ddf0194cf28a0845ae51b9503841ca880912
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="idispeventimpl-class"></a>Класс IDispEventImpl
Этот класс предоставляет реализации `IDispatch` методы.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```  
  
#### <a name="parameters"></a>Параметры  
 `nID`  
 Уникальный идентификатор для исходного объекта. Если `IDispEventImpl` является базовым классом для составного элемента управления, используйте идентификатор ресурса для нужного элемента управления в контейнере для этого параметра. В других случаях используйте произвольное целое положительное число.  
  
 `T`  
 Класс пользователя, который является производным от `IDispEventImpl`.  
  
 `pdiid`  
 Указатель на IID интерфейс событий, реализованные этим классом. Этот интерфейс должен быть определен в библиотеке типов, обозначенное с помощью `plibid`, `wMajor`, и `wMinor`.  
  
 `plibid`  
 Указатель на библиотеку типов, которая определяет интерфейс диспетчеризации, на который указывает `pdiid`. Если **& GUID_NULL**, будет загрузить библиотеку типов из источников событий объекта.  
  
 `wMajor`  
 Основной номер версии для библиотеки типов. Значение по умолчанию — 0.  
  
 `wMinor`  
 Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.  
  
 `tihclass`  
 Класс, используемый для управления сведения о типе `T`. Значение по умолчанию — класс типа `CComTypeInfoHolder`, однако можно переопределить, указав класс типа, отличного от этого параметра шаблона `CComTypeInfoHolder`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Класс, используемый для управления сведения о типе. По умолчанию `CComTypeInfoHolder`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Находит индекс функция указанный идентификатор.|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Сопоставляется соответствующему набору целого DISPID один элемент и дополнительный набор имен аргументов.|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Извлекает сведения о типе для объекта.|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Возвращает число интерфейсов сведения о типе.|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Возвращает базовый тип определяемого пользователем типа.|  
  
## <a name="remarks"></a>Примечания  
 `IDispEventImpl`предоставляет способ реализации диспетчерский интерфейс событий без необходимости указать код реализации для каждого метода и события в этом интерфейсе. `IDispEventImpl`предоставляет реализации `IDispatch` методы. Необходимо предоставить реализации для событий, которые нужно в обработке.  
  
 `IDispEventImpl`работает совместно с картой приемника событий в классе направляет события соответствующим функциям обработки. С помощью этого класса:  
  

 Добавить [SINK_ENTRY](composite-control-macros.md#sink_entry) или [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) макрос карту приемник событий для каждого события для каждого объекта, которые требуется обработать. При использовании `IDispEventImpl` как базовый класс составного элемента управления, можно вызвать [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) для установки и разорвать соединение с источниками событий для всех операций приемника событий карты. В других случаях или расширить возможности управления, вызовите [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) для установления соединения между исходным объектом и базового класса. Вызовите [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) Чтобы разорвать связь.  

  
 Должен быть производным от `IDispEventImpl` (с помощью уникальное значение для `nID`) для каждого объекта, для которого необходимы для обработки событий. Вы можете использовать базовый класс, unadvising от одного исходного объекта, затем о том, для исходного объекта, но максимальное количество объектов источников, может обрабатываться одновременно с помощью одного объекта ограничивается количество `IDispEventImpl` базовые классы.  
  
 `IDispEventImpl`предоставляет те же функциональные возможности, как [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), за исключением того, он возвращает тип сведений об интерфейсе из библиотеки типов, вместо того, он предоставлен как указатель на [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) Структура. Используйте `IDispEventSimpleImpl` при не имеют библиотеку типов, описывающие интерфейса события или хотите избежать издержек, связанных с использованием библиотеки типов.  
  
> [!NOTE]
> `IDispEventImpl`и `IDispEventSimpleImpl` предоставить свою собственную реализацию **IUnknown::QueryInterface** включение каждого `IDispEventImpl` и `IDispEventSimpleImpl` базового класса в качестве отдельный идентификатор COM по-прежнему предоставляя прямой доступ к классу элементы в основной COM-объект.  
  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из вашего методы обработчиков событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
 Дополнительные сведения см. в разделе [IDispEventImpl поддержки](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId  
 Находит индекс функция указанный идентификатор.  
  
```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Ссылка на идентификатор функции.  
  
 *dispidMember*  
 [in] Идентификатор диспетчеризации функции.  
  
 `lcid`  
 [in] Контекст языкового стандарта идентификатора функции.  
  
 `info`  
 [in] Структура, указывающее, как вызвать функцию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames  
 Сопоставляет один элемент и дополнительный набор имен аргументов соответствующему набору целого DispId, которые могут быть использованы при последующих вызовах [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [:: GetIdsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) в Windows SDK.  
  
##  <a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo  
 Возвращает сведения о типе объекта, которые затем могут использоваться для получения сведений о типе интерфейса.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount  
 Возвращает количество предоставляемых объектом интерфейсов для доступа к сведениям о типе (0 или 1).  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) в Windows SDK.  
  
##  <a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType  
 Возвращает базовый тип определяемого пользователем типа.  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>Параметры  
 `pTI`  
 [in] Указатель на [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) интерфейса, содержащего определяемый пользователем тип.  
  
 *hrt*  
 [in] Дескриптор для описания типа, который требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип variant.  
  
### <a name="remarks"></a>Примечания  
 В разделе [ITypeInfo::GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00).  
  
##  <a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl  
 Конструктор. Хранит значения параметров шаблона класса `plibid`, `pdiid`, `wMajor`, и `wMinor`.  
  
```
IDispEventImpl();
```  
  
##  <a name="tihclass"></a>IDispEventImpl::tihclass  
 Это определение типа является экземпляром типа параметра шаблона класса `tihclass`.  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию класс является `CComTypeInfoHolder`. `CComTypeInfoHolder`Управляет сведения о типе для класса.  
  
## <a name="see-also"></a>См. также  
 [Структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)   
 [Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)   
 [Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](composite-control-macros.md#sink_entry)   
 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)