---
title: Класс IViewObjectExImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ec04a1113cd14824db8e354653f5f7fcb108742
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215347"
---
# <a name="iviewobjecteximpl-class"></a>Класс IViewObjectExImpl
Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), и [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) интерфейсов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IViewObjectExImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|Рисует представление элемента управления на контекст устройства.|  
|[IViewObjectExImpl::Freeze](#freeze)|Замораживает формируемого представление элемента управления, поэтому он не изменится до `Unfreeze`. Реализация ATL возвращает E_NOTIMPL.|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|Извлекает существующее соединение приемнике уведомлений на элементе управления, если таковой имеется.|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Возвращает логическую палитру, используемые элементом управления для рисования. Реализация ATL возвращает E_NOTIMPL.|  
|[IViewObjectExImpl::GetExtent](#getextent)|Получает отображаемый размер элемента управления в единицах HIMETRIC (0,01 мм на единицу) из данные-член класса элемента управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Предоставляет подсказки контейнера по объект, который используется при изменении размеров его.|  
|[IViewObjectExImpl::GetRect](#getrect)|Возвращает прямоугольник, описывающий запрошенный вид рисования. Реализация ATL возвращает E_NOTIMPL.|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Возвращает информацию о размытости объекта и поддерживаемых способах рисования.|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Проверяет, если указанная точка находится в указанный прямоугольник и возвращает [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) значение в `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Проверяет ли прямоугольник отображения элемента управления перекрывается любой точки в указанное расположение прямоугольника и возвращает значение HITRESULT в `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|Настраивает подключение между элементом управления и приемника уведомлений, чтобы приемник может получать уведомления об изменениях в представлении элемента управления.|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Снимает формируемого представление элемента управления. Реализация ATL возвращает E_NOTIMPL.|  
  
## <a name="remarks"></a>Примечания  
 [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), и [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) интерфейсы позволяют элемент управления отображать себя напрямую, а также для создания и управления приемника уведомлений для уведомления контейнер для изменения отображения элемента управления. `IViewObjectEx` Интерфейс обеспечивает поддержку для функций расширенного элемента управления, таких как рисование без мелькания, непрямоугольные и прозрачные элементы управления и нажатия (например, насколько близко щелчка кнопкой мыши необходимо следует учитывать в элементе управления). Класс `IViewObjectExImpl` предоставляет стандартную реализацию этих интерфейсов и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="draw"></a>  IViewObjectExImpl::Draw  
 Рисует представление элемента управления на контекст устройства.  
  
```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод `CComControl::OnDrawAdvanced` которое в свою очередь вызывает класс элемента управления `OnDraw` метод. `OnDraw` Автоматически добавляется метод к классу элемента управления при создании элемента управления с помощью мастера управления ATL. По умолчанию мастер `OnDraw` рисует прямоугольник с надписью «ATL 3.0».  
  
 См. в разделе [IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw) в Windows SDK.  
  
##  <a name="freeze"></a>  IViewObjectExImpl::Freeze  
 Замораживает формируемого представление элемента управления, поэтому он не изменится до `Unfreeze`. Реализация ATL возвращает E_NOTIMPL.  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IViewObject::Freeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-freeze) в Windows SDK.  
  
##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise  
 Извлекает существующее соединение приемнике уведомлений на элементе управления, если таковой имеется.  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>Примечания  
 Приемник хранится в данные-член класса элемента управления [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).  
  
 См. в разделе [IViewObject::GetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getadvise) в Windows SDK.  
  
##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet  
 Возвращает логическую палитру, используемые элементом управления для рисования. Реализация ATL возвращает E_NOTIMPL.  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IViewObject::GetColorSet](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getcolorset) в Windows SDK.  
  
##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent  
 Получает отображаемый размер элемента управления в единицах HIMETRIC (0,01 мм на единицу) из данные-член класса элемента управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IViewObject2::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-iviewobject2-getextent) в Windows SDK.  
  
##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent  
 Предоставляет подсказки контейнера по объект, который используется при изменении размеров его.  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>Примечания  
 Если `dwAspect` — DVASPECT_CONTENT и *pExtentInfo "->" dwExtentMode* является DVEXTENT_CONTENT, задает * `psizel` на данные-член класса элемента управления [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). В противном случае возвращает ошибку HRESULT.  
  
 См. в разделе [IViewObjectEx::GetNaturalExtent](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) в Windows SDK.  
  
##  <a name="getrect"></a>  IViewObjectExImpl::GetRect  
 Возвращает прямоугольник, описывающий запрошенный вид рисования. Реализация ATL возвращает E_NOTIMPL.  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IViewObjectEx::GetRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getrect) в Windows SDK.  
  
##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus  
 Возвращает информацию о размытости объекта и поддерживаемых способах рисования.  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию задает ATL `pdwStatus` для указания, что элемент управления поддерживает VIEWSTATUS_OPAQUE (возможные значения приведены в [Просмотр СОСТОЯНИЯ](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) перечисления).  
  
 См. в разделе [IViewObjectEx::GetViewStatus](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) в Windows SDK.  
  
##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint  
 Проверяет, если указанная точка находится в указанный прямоугольник и возвращает [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) значение в `pHitResult`.  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Примечания  
 Значение может быть HITRESULT_HIT или HITRESULT_OUTSIDE.  
  
 Если `dwAspect` равно [DVASPECT_CONTENT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), метод возвращает значение S_OK. В противном случае метод возвращает значение E_FAIL.  
  
 См. в разделе [IViewObjectEx::QueryHitPoint](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) в Windows SDK.  
  
##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect  
 Проверяет ли прямоугольник отображения элемента управления перекрывается любой точки в указанное расположение прямоугольника и возвращает [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) значение в `pHitResult`.  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Примечания  
 Значение может быть HITRESULT_HIT или HITRESULT_OUTSIDE.  
  
 Если `dwAspect` равно [DVASPECT_CONTENT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), метод возвращает значение S_OK. В противном случае метод возвращает значение E_FAIL.  
  
 См. в разделе [IViewObjectEx::QueryHitRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) в Windows SDK.  
  
##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise  
 Настраивает подключение между элементом управления и приемника уведомлений, чтобы приемник может получать уведомления об изменениях в представлении элемента управления.  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>Примечания  

 Указатель на [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) интерфейс в приемнике уведомлений, хранится в данные-член класса элемента управления [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).  

  
 См. в разделе [IViewObject::SetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-setadvise) в Windows SDK.  
  
##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze  
 Снимает формируемого представление элемента управления. Реализация ATL возвращает E_NOTIMPL.  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IViewObject::Unfreeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-unfreeze) в Windows SDK.  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 Реализуйте этот метод, чтобы закрыть дескриптор, связанный с данным объектом.  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>Параметры  
 *hHandle*  
 Дескриптор будет закрыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успеха или ошибку HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор, переданный этому методу был ранее связан с данным объектом, с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 Реализуйте этот метод для выполнения кода при оповещенным, дескриптор, связанный с данным объектом.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Параметры  
 *dwParam*  
 Параметр user.  
  
 *hObject*  
 Дескриптор, который оповещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успеха или ошибку HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор и DWORD/указатель, переданный этому методу ранее был связан с данным объектом с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Интерфейсы, элементы управления ActiveX](/windows/desktop/com/activex-controls-interfaces)   
 [Учебник](../../atl/active-template-library-atl-tutorial.md)   
 [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
