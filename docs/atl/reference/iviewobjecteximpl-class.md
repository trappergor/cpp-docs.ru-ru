---
title: "Класс IViewObjectExImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.openlocfilehash: 2b585a056324507cc631e64e6dbe9d0ed610361d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iviewobjecteximpl-class"></a>Класс IViewObjectExImpl
Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), и [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) интерфейсов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IViewObjectExImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|Рисует представление элемента управления на контекст устройства.|  
|[IViewObjectExImpl::Freeze](#freeze)|Замораживает формируемого представление элемента управления, он не изменится до `Unfreeze`. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|Извлекает подключение приемнике уведомлений на элементе управления, при наличии.|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Возвращает логический палитры, используемого элементом управления для рисования. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](#getextent)|Получает размер отображения элемента управления в единицы HIMETRIC (0,01 мм на единицу) из элемента управления класса данных [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Предоставляет контейнер для объекта для использования при изменении размеров его подсказки.|  
|[IViewObjectExImpl::GetRect](#getrect)|Возвращает прямоугольник, описывающий запрошенный вид рисования. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Возвращает информацию о размытости объекта и какие рисования поддерживаются.|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Проверяет, если заданная точка находится в заданном прямоугольнике и возвращает [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) значение в `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Проверяет ли прямоугольник отображения элемента управления перекрывается любую точку в указанное расположение прямоугольника и возвращает **HITRESULT** значение в `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|Устанавливает соединение между элементом управления и приемника уведомлений приемник может уведомления об изменениях в представлении элемента управления.|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Снимает формируемого представление элемента управления. Возвращает реализацию ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Примечания  
 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), и [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) интерфейсы управления для отображения самой напрямую и для создания и управления приемника уведомлений для уведомления контейнера изменения отображения элемента управления. **IViewObjectEx** интерфейс обеспечивает поддержку функций расширенного элемента управления как мерцания рисования, непрямоугольных и прозрачность элементов управления и нажатия (например, насколько близко щелчок мыши должен находиться считается на элементе управления). Класс `IViewObjectExImpl` предоставляет стандартную реализацию этих интерфейсов и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="draw"></a>IViewObjectExImpl::Draw  
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
 Этот метод вызывает метод **CComControl::OnDrawAdvanced** которого, в свою очередь, вызывает класс элемента управления `OnDraw` метод. `OnDraw` Автоматически добавляется метод к классу элемента управления при создании элемента управления с помощью мастера элементов управления ATL. По умолчанию мастер `OnDraw` Рисование прямоугольника с меткой «ATL 3.0».  
  
 В разделе [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="freeze"></a>IViewObjectExImpl::Freeze  
 Замораживает формируемого представление элемента управления, он не изменится до `Unfreeze`. Возвращает реализацию ATL **E_NOTIMPL**.  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getadvise"></a>IViewObjectExImpl::GetAdvise  
 Извлекает подключение приемнике уведомлений на элементе управления, при наличии.  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>Примечания  
 Уведомлять приемник хранится в элемент управления класса данных [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).  
  
 В разделе [IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcolorset"></a>IViewObjectExImpl::GetColorSet  
 Возвращает логический палитры, используемого элементом управления для рисования. Возвращает реализацию ATL **E_NOTIMPL**.  
  
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
 В разделе [IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getextent"></a>IViewObjectExImpl::GetExtent  
 Получает размер отображения элемента управления в единицы HIMETRIC (0,01 мм на единицу) из элемента управления класса данных [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnaturalextent"></a>IViewObjectExImpl::GetNaturalExtent  
 Предоставляет контейнер для объекта для использования при изменении размеров его подсказки.  
  
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
 Если `dwAspect` — `DVASPECT_CONTENT` и *pExtentInfo-> dwExtentMode* — **DVEXTENT_CONTENT**, задает * `psizel` для члена данных класса управления [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). В противном случае — возвращает сообщение об ошибке `HRESULT`.  
  
 В разделе [IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getrect"></a>IViewObjectExImpl::GetRect  
 Возвращает прямоугольник, описывающий запрошенный вид рисования. Возвращает реализацию ATL **E_NOTIMPL**.  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getviewstatus"></a>IViewObjectExImpl::GetViewStatus  
 Возвращает информацию о размытости объекта и какие рисования поддерживаются.  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию устанавливает ATL `pdwStatus` для указания, что элемент управления поддерживает **VIEWSTATUS_OPAQUE** (возможные значения приведены в [Просмотр СОСТОЯНИЯ](http://msdn.microsoft.com/library/windows/desktop/ms687201) перечисления).  
  
 В разделе [IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="queryhitpoint"></a>IViewObjectExImpl::QueryHitPoint  
 Проверяет, если заданная точка находится в заданном прямоугольнике и возвращает [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) значение в `pHitResult`.  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Примечания  
 Значение может быть либо **HITRESULT_HIT** или **HITRESULT_OUTSIDE**.  
  
 Если `dwAspect` равняется [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), метод возвращает `S_OK`. В противном случае, метод возвращает **E_FAIL**.  
  
 В разделе [IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="queryhitrect"></a>IViewObjectExImpl::QueryHitRect  
 Проверяет ли прямоугольник отображения элемента управления перекрывается любую точку в указанное расположение прямоугольника и возвращает [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) значение в `pHitResult`.  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Примечания  
 Значение может быть либо **HITRESULT_HIT** или **HITRESULT_OUTSIDE**.  
  
 Если `dwAspect` равняется [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), метод возвращает `S_OK`. В противном случае, метод возвращает **E_FAIL**.  
  
 В разделе [IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setadvise"></a>IViewObjectExImpl::SetAdvise  
 Устанавливает соединение между элементом управления и приемника уведомлений приемник может уведомления об изменениях в представлении элемента управления.  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>Примечания  

 Указатель на [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) интерфейса на приемник уведомлений хранятся в элемент управления класса данных [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).  

  
 В разделе [IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="unfreeze"></a>IViewObjectExImpl::Unfreeze  
 Снимает формируемого представление элемента управления. Возвращает реализацию ATL **E_NOTIMPL**.  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 Реализация этого метода, чтобы закрыть дескриптор, связанный с данным объектом.  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>Параметры  
 *hHandle*  
 Дескриптор будет закрыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Маркер, переданный этому методу был ранее связан с этим объектом, с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities&#135;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
 Реализация этого метода для выполнения кода при оповещенным, дескриптор, связанный с данным объектом.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Параметры  
 `dwParam`  
 Параметр user.  
  
 `hObject`  
 Дескриптор, который будет отправлен сигнал.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор и DWORD-указатель, передаваемый этому методу ранее были связаны с этим объектом с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities&#136;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Интерфейсы, элементы управления ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Учебник](../../atl/active-template-library-atl-tutorial.md)   
 [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

