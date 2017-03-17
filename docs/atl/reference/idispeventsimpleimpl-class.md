---
title: "Класс IDispEventSimpleImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
caps.latest.revision: 27
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
ms.openlocfilehash: 6b7bc2c64139726f84f1c19c7d6b40e8d68cdc18
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventsimpleimpl-class"></a>Класс IDispEventSimpleImpl
Этот класс предоставляет реализацию `IDispatch` методы без получения информации о типе из библиотеки типов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>Параметры  
 `nID`  
 Уникальный идентификатор для исходного объекта. Если `IDispEventSimpleImpl` является базовым классом для составного элемента управления, используйте идентификатор ресурса для нужного элемента управления в контейнере для этого параметра. В других случаях используйте произвольное целое положительное число.  
  
 `T`  
 Класс пользователя, который является производным от `IDispEventSimpleImpl`.  
  
 `pdiid`  
 Указатель на идентификатор IID disp-интерфейс событий, реализованные этим классом.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|Устанавливает соединение с источником события по умолчанию.|  
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|Устанавливает соединение с источником события.|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Разрывает соединение с источником события.|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|Возвращает **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|Возвращает **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|Возвращает **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](#invoke)|Вызывает обработчики событий в событии указаны приемником сопоставления.|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Разрывает соединение с источником события по умолчанию.|  
  
## <a name="remarks"></a>Примечания  
 `IDispEventSimpleImpl`предоставляет способ реализации диспетчерский интерфейс событий без необходимости предоставить код реализации для каждого метода или события в этом интерфейсе. `IDispEventSimpleImpl`предоставляет реализацию `IDispatch` методы. Необходимо предоставлять реализации для событий, которые нужно в обработке.  
  
 `IDispEventSimpleImpl`работает совместно с [картой приемника событий](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f) в классе, распределяя события соответствующим функциям обработки. С помощью этого класса:  
  
-   Добавить [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7) макрос картой приемника событий для каждого события на каждый объект, который необходимо обработать.  
  
-   Укажите сведения о типе для каждого события, передав указатель [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) структуру в качестве параметра для каждой записи. На x86 платформы, `_ATL_FUNC_INFO.cc` значение должно быть CC_CDECL с помощью вызова метода __stdcall функции обратного вызова.  
  
-   Вызов [DispEventAdvise](#dispeventadvise) для установления соединения между исходным объектом и базового класса.  
  
-   Вызов [DispEventUnadvise](#dispeventunadvise) Чтобы разорвать подключение.  
  
 Должен быть производным от `IDispEventSimpleImpl` (с помощью уникальное значение для `nID`) для каждого объекта, для которого необходимы для обработки событий. Можно повторно использовать базовый класс, unadvising от одного исходного объекта, затем о том, с другой исходный объект, но максимальное число объектов источника, которые могут обрабатываться один объект за раз, ограничивается число `IDispEventSimpleImpl` базовые классы.  
  
 **IDispEventSimplImpl** предоставляет те же функции, как [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), но он не получает тип сведений об интерфейсе из библиотеки типов. Мастер создает код, основанные только на `IDispEventImpl`, но можно использовать `IDispEventSimpleImpl` , добавив код вручную. Использование `IDispEventSimpleImpl` при отсутствии библиотеки типов, описывающий интерфейс событий или чтобы избежать издержек, связанных с использованием библиотеки типов.  
  
> [!NOTE]
> `IDispEventImpl`и `IDispEventSimpleImpl` собственные реализации **IUnknown::QueryInterface** включения каждого `IDispEventImpl` или `IDispEventSimpleImpl` базового класса в качестве с отдельным удостоверением COM по-прежнему предоставляя прямой доступ к членам класса в основной COM-объект.  
  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
 Дополнительные сведения см. в разделе [IDispEventImpl поддержки](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="advise"></a>IDispEventSimpleImpl::Advise  
 Этот метод вызывается для установления соединения с источником события, представленного *pUnk*.  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на **IUnknown** интерфейс объект источника события.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`или любой сбой `HRESULT` значение.  
  
### <a name="remarks"></a>Примечания  
 После установления соединения событие, возникающее из *pUnk* будут направляться на обработчики в вашем классе посредством картой приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо различать вызовы этого метода с областью, вы заинтересованы в вызов с определенного базового класса.  
  
 `Advise`Устанавливает соединение с источником событий по умолчанию, он получает идентификатор IID источника события по умолчанию объекта определяется [AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155).  
  
##  <a name="dispeventadvise"></a>IDispEventSimpleImpl::DispEventAdvise  
 Этот метод вызывается для установления соединения с источником события, представленного *pUnk*.  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на **IUnknown** интерфейс объект источника события.  
  
 `piid`  
 Указатель на идентификатор IID объект источника события.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`или любой сбой `HRESULT` значение.  
  
### <a name="remarks"></a>Примечания  
 Следовательно, события, запускаемые из *pUnk* будут направляться на обработчики в вашем классе посредством картой приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо различать вызовы этого метода с областью, вы заинтересованы в вызов с определенного базового класса.  
  
 `DispEventAdvise`Устанавливает соединение с источником события, указанного в `pdiid`.  
  
##  <a name="dispeventunadvise"></a>IDispEventSimpleImpl::DispEventUnadvise  
 Разрывает соединение с источником события, представленного *pUnk*.  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на **IUnknown** интерфейс объект источника события.  
  
 `piid`  
 Указатель на идентификатор IID объект источника события.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`или любой сбой `HRESULT` значение.  
  
### <a name="remarks"></a>Примечания  
 Когда соединение разрывается, события больше не будет перенаправлен к функции обработчика в картой приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо различать вызовы этого метода с областью, вы заинтересованы в вызов с определенного базового класса.  
  
 `DispEventAdvise`разрывает соединение, которое было установлено с источником события, указанного в `pdiid`.  
  
##  <a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames  
 Эта реализация **IDispatch::GetIdsOfNames расширенное** возвращает **E_NOTIMPL**.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetIdsOfNames расширенное](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo  
 Эта реализация **IDispatch::GetTypeInfo** возвращает **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount  
 Эта реализация **IDispatch::GetTypeInfoCount** возвращает **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="invoke"></a>IDispEventSimpleImpl::Invoke  
 Эта реализация **IDispatch::Invoke** вызывает обработчики событий указанного в описании события приемником сопоставления.  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
##  <a name="unadvise"></a>IDispEventSimpleImpl::Unadvise  
 Разрывает соединение с источником события, представленного *pUnk*.  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на **IUnknown** интерфейс объект источника события.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`или любой сбой `HRESULT` значение.  
  
### <a name="remarks"></a>Примечания  
 Когда соединение разрывается, события больше не будет перенаправлен к функции обработчика в картой приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо различать вызовы этого метода с областью, вы заинтересованы в вызов с определенного базового класса.  
  
 `Unadvise`разрывает соединение, которое было установлено с источником событий по умолчанию, указанные в `pdiid`.  
  
 **Unavise** разрыва соединения с источником события по умолчанию получает идентификатор IID источника события по умолчанию объекта определяется [AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155).  
  
## <a name="see-also"></a>См. также  
 [Структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)   
 [Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)   
 [Класс IDispEventImpl](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

