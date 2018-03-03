---
title: "Класс IDispEventSimpleImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8a5b3098961af4f3f9262cdc4c99dbe80b4ac7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="idispeventsimpleimpl-class"></a>Класс IDispEventSimpleImpl
Этот класс предоставляет реализации `IDispatch` методы без получения сведений о типе из библиотеки типов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
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
 Указатель на IID интерфейс событий, реализованные этим классом.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|Устанавливает соединение с источником событий по умолчанию.|  
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|Устанавливает соединение с источником события.|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Разрывает соединение с источником события.|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|Возвращает **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|Возвращает **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|Возвращает **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](#invoke)|Вызывает обработчики событий указанного в описании события приемником сопоставления.|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Разрывает соединение с источником событий по умолчанию.|  
  
## <a name="remarks"></a>Примечания  
 `IDispEventSimpleImpl`предоставляет способ реализации диспетчерский интерфейс событий без необходимости указать код реализации для каждого метода и события в этом интерфейсе. `IDispEventSimpleImpl`предоставляет реализации `IDispatch` методы. Необходимо предоставить реализации для событий, которые нужно в обработке.  
  
 `IDispEventSimpleImpl`работает совместно с картой приемника событий в классе направляет события соответствующим функциям обработки. С помощью этого класса:  
  
-   Добавить [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) макрос карту приемник событий для каждого события для каждого объекта, которые требуется обработать.  
  
-   Передавать сведения о типе для каждого события, передав указатель [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) структуру как параметр для каждой записи. На x86 платформы, `_ATL_FUNC_INFO.cc` значение должно быть CC_CDECL с помощью вызова метода __stdcall функции обратного вызова.  
  
-   Вызовите [DispEventAdvise](#dispeventadvise) для установления соединения между исходным объектом и базового класса.  
  
-   Вызовите [DispEventUnadvise](#dispeventunadvise) Чтобы разорвать связь.  
  
 Должен быть производным от `IDispEventSimpleImpl` (с помощью уникальное значение для `nID`) для каждого объекта, для которого необходимы для обработки событий. Вы можете использовать базовый класс, unadvising от одного исходного объекта, затем о том, для исходного объекта, но максимальное количество объектов источников, может обрабатываться одновременно с помощью одного объекта ограничивается количество `IDispEventSimpleImpl` базовые классы.  
  
 **IDispEventSimplImpl** предоставляет те же функциональные возможности, как [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), но он не получает сведения о типе об интерфейсе из библиотеки типов. Мастер создает код только на основе `IDispEventImpl`, но вы можете использовать `IDispEventSimpleImpl` путем добавления кода вручную. Используйте `IDispEventSimpleImpl` при не имеют библиотеку типов, описывающие интерфейса события или хотите избежать издержек, связанных с использованием библиотеки типов.  
  
> [!NOTE]
> `IDispEventImpl`и `IDispEventSimpleImpl` предоставить свою собственную реализацию **IUnknown::QueryInterface** включение каждого `IDispEventImpl` или `IDispEventSimpleImpl` базового класса в качестве отдельный идентификатор COM по-прежнему предоставляя прямой доступ к членам класса в основной COM-объект.  
  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из вашего методы обработчиков событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
 Дополнительные сведения см. в разделе [IDispEventImpl поддержки](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
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
 После установления соединения, события, запускаемые из *pUnk* будут направляться на обработчики класса посредством схеме приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызова этого метода с областью, вызов с определенного базового класса, которые вас интересуют.  
  
 `Advise`Устанавливает соединение с источником событий по умолчанию, он получает идентификатор IID источника события по умолчанию объекта определяется [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).  
  
##  <a name="dispeventadvise"></a>IDispEventSimpleImpl::DispEventAdvise  
 Этот метод вызывается для установления соединения с источником события, представленного *pUnk*.  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на **IUnknown** интерфейс объект источника события.  
  
 `piid`  
 Указатель на IID объект источника события.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`или любой сбой `HRESULT` значение.  
  
### <a name="remarks"></a>Примечания  
 Следовательно, события, запускаемые из *pUnk* будут направляться на обработчики класса посредством схеме приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызова этого метода с областью, вызов с определенного базового класса, которые вас интересуют.  
  
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
 Указатель на IID объект источника события.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`или любой сбой `HRESULT` значение.  
  
### <a name="remarks"></a>Примечания  
 Как только подключение разорвано, события больше не направляются в функции обработчика, перечисленный в карте приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызова этого метода с областью, вызов с определенного базового класса, которые вас интересуют.  
  
 `DispEventAdvise`разрывает соединение, которое было установлено с источником события, указанного в `pdiid`.  
  
##  <a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames  
 Эта реализация **:: GetIdsOfNames** возвращает **E_NOTIMPL**.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [:: GetIdsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) в Windows SDK.  
  
##  <a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo  
 Эта реализация **IDispatch::GetTypeInfo** возвращает **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) в Windows SDK.  
  
##  <a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount  
 Эта реализация **IDispatch::GetTypeInfoCount** возвращает **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) в Windows SDK.  
  
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
 Как только подключение разорвано, события больше не направляются в функции обработчика, перечисленный в карте приемника событий.  
  
> [!NOTE]
>  Если класс является производным из нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызова этого метода с областью, вызов с определенного базового класса, которые вас интересуют.  
  
 `Unadvise`разрывает соединение, которое было установлено с источником событий по умолчанию, указанное в `pdiid`.  
  
 **Unavise** разрыве соединения с источником событий по умолчанию, он получает идентификатор IID источника события по умолчанию для объекта, как определено [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).  
  
## <a name="see-also"></a>См. также  
 [Структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)   
 [Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)   
 [Класс IDispEventImpl](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
