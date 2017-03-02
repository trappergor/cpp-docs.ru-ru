---
title: "Класс IDispEventImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 235955f8573ae7e430be3de2a96efdd7496d15de
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventimpl-class"></a>Класс IDispEventImpl
Этот класс предоставляет реализацию `IDispatch` методы.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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
 Указатель на идентификатор IID disp-интерфейс событий, реализованные этим классом. Этот интерфейс должен быть определен в библиотеке типов, обозначенное с помощью `plibid`, `wMajor`, и `wMinor`.  
  
 `plibid`  
 Указатель, определяющий интерфейс диспетчеризации библиотеки типов, на который указывает `pdiid`. Если **& GUID_NULL**, будет загрузить библиотеку типов из источников событий объекта.  
  
 `wMajor`  
 Основной номер версии библиотеки типов. Значение по умолчанию — 0.  
  
 `wMinor`  
 Дополнительный номер версии библиотеки типов. Значение по умолчанию — 0.  
  
 `tihclass`  
 Класс, используемый для управления сведения о типе `T`. Значение по умолчанию — класс типа `CComTypeInfoHolder`, однако можно переопределить этот параметр шаблона, не предоставляя класс типа `CComTypeInfoHolder`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Класс, используемый для управления сведения о типе. По умолчанию `CComTypeInfoHolder`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Находит индекс функция заданным идентификатором диспетчеризации.|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Сопоставляется с соответствующим набором целое DISPID один элемент и необязательный набор имен аргументов.|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Извлекает сведения о типе объекта.|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Получает число интерфейсов сведения о типе.|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Получает базовый тип определяемого пользователем типа.|  
  
## <a name="remarks"></a>Примечания  
 `IDispEventImpl`предоставляет способ реализации диспетчерский интерфейс событий без необходимости предоставить код реализации для каждого метода или события в этом интерфейсе. `IDispEventImpl`предоставляет реализацию `IDispatch` методы. Необходимо предоставлять реализации для заинтересованы в обработке событий.  
  
 `IDispEventImpl`работает совместно с [картой приемника событий](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f) в классе, распределяя события соответствующим функциям обработки. С помощью этого класса:  
  

 Добавить [SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5) или [SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac) макрос картой приемника событий для каждого события на каждый объект, который необходимо обработать. При использовании `IDispEventImpl` как базовый класс составного элемента управления, можно вызвать [AtlAdviseSinkMap](http://msdn.microsoft.com/library/0757a6af-3de3-4179-8b4f-ccd137d919b4) для установки и разорвать соединение с источниками событий для всех записей событий приемника карты. В других случаях или расширить возможности управления, вызовите [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) для установления соединения между исходным объектом и базового класса. Вызов [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) Чтобы разорвать подключение.  

  
 Должен быть производным от `IDispEventImpl` (с помощью уникальное значение для `nID`) для каждого объекта, для которого необходимы для обработки событий. Можно повторно использовать базовый класс, unadvising от одного исходного объекта, затем о том, с другой исходный объект, но максимальное число объектов источника, которые могут обрабатываться один объект за раз, ограничивается число `IDispEventImpl` базовые классы.  
  
 `IDispEventImpl`предоставляет те же функции, как [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), но она возвращает тип сведений об интерфейсе из библиотеки типов, вместо того, он предоставлен как указатель на [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) структуры. Использование `IDispEventSimpleImpl` при не библиотеку типов, описывающий интерфейс событий, так и избежать издержек, связанных с использованием библиотеки типов.  
  
> [!NOTE]
> `IDispEventImpl`и `IDispEventSimpleImpl` собственные реализации **IUnknown::QueryInterface** включения каждого `IDispEventImpl` и `IDispEventSimpleImpl` базового класса в качестве с отдельным удостоверением COM по-прежнему предоставляя прямой доступ к членам класса в основной COM-объект.  
  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
 Дополнительные сведения см. в разделе [IDispEventImpl поддержки](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-namegetfuncinfofromida--idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId  
 Находит индекс функция заданным идентификатором диспетчеризации.  
  
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
 [in] Контекст языкового идентификатора функции.  
  
 `info`  
 [in] Структура, указывающее способ вызова функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="a-namegetidsofnamesa--idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames  
 Один член и необязательный набор имен аргументов сопоставляется соответствующему набору целого идентификаторы DispId, которые могут быть использованы при последующих вызовах [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetIdsOfNames расширенное](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettypeinfoa--idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo  
 Возвращает сведения о типе объекта, которые затем могут использоваться для получения сведений о типе интерфейса.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettypeinfocounta--idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount  
 Возвращает количество предоставляемых объектом интерфейсов для доступа к сведениям о типе (0 или 1).  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetuserdefinedtypea--idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType  
 Получает базовый тип определяемого пользователем типа.  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>Параметры  
 `pTI`  
 [in] Указатель на [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) интерфейс, содержащий определяемого пользователем типа.  
  
 *hrt*  
 [in] Дескриптор для описания типа для извлечения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип variant.  
  
### <a name="remarks"></a>Примечания  
 В разделе [ITypeInfo::GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00).  
  
##  <a name="a-nameidispeventimpla--idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl  
 Конструктор. Сохраняет значения параметров шаблона класса `plibid`, `pdiid`, `wMajor`, и `wMinor`.  
  
```
IDispEventImpl();
```  
  
##  <a name="a-nametihclassa--idispeventimpltihclass"></a><a name="tihclass"></a>IDispEventImpl::tihclass  
 Это определение типа является экземпляром класса параметр шаблона `tihclass`.  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию класс является `CComTypeInfoHolder`. `CComTypeInfoHolder`Управляет сведения о типе для класса.  
  
## <a name="see-also"></a>См. также  
 [Структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)   
 [Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)   
 [Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5)   
 [SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
