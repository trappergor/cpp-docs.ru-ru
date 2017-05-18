---
title: "Класс CAxWindow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 202c68fa4044a7c7a6c47c52b8095c5e7227b56d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="caxwindow-class"></a>Класс CAxWindow
Этот класс предоставляет методы для работы с окном размещения элемента управления ActiveX.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Присоединяет существующего элемента управления ActiveX для `CAxWindow` объекта.|  
|[CAxWindow](#caxwindow)|Создает объект `CAxWindow`.|  
|[CreateControl](#createcontrol)|Создает элемент управления ActiveX, инициализирует его и размещает его в `CAxWindow` окна.|  
|[CreateControlEx](#createcontrolex)|Создает элемент управления ActiveX и получает указатель на интерфейс (или указатели) с элементом управления.|  
|[GetWndClassName](#getwndclassname)|(Статический) Извлекает имя предварительно определенный класс `CAxWindow` объекта.|  
|[QueryControl](#querycontrol)|Извлекает **IUnknown** размещенного элемента управления ActiveX.|  
|[QueryHost](#queryhost)|Извлекает **IUnknown** указатель `CAxWindow` объекта.|  
|[SetExternalDispatch](#setexternaldispatch)|Задает интерфейс внешнего диспетчеризации, используемые `CAxWindow` объекта.|  
|[SetExternalUIHandler](#setexternaluihandler)|Задает внешние **IDocHostUIHandler** интерфейс, используемый `CAxWindow` объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Назначает **HWND** к существующему **CAxWindow** объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для управления окна, содержащего элемент управления ActiveX. Размещение обеспечивается» **AtlAxWin80»**, который является оболочкой для `CAxWindow`.  
  
 Класс `CAxWindow` реализуется как специализацию `CAxWindowT` класса. Данная специализация объявляется как:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Если необходимо изменить базовый класс, можно использовать `CAxWindowT` и укажите новый базовый класс в качестве аргумента шаблона.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="attachcontrol"></a>CAxWindow::AttachControl  
 Создает новый объект узла, если уже не существуют и прикрепляет к узлу указанного элемента управления.  
  
```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 [in] Указатель на **IUnknown** элемента управления.  
  
 `ppUnkContainer`  
 [out] Указатель на **IUnknown** узла ( **AxWin** объекта).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Присоединяемый объект управления необходимо правильно инициализировать перед вызовом метода `AttachControl`.  
  
##  <a name="caxwindow"></a>CAxWindow::CAxWindow  
 Создает `CAxWindow` объекта с помощью существующего объекта дескриптора окна.  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 Дескриптор существующего объекта окна.  
  
##  <a name="createcontrol"></a>CAxWindow::CreateControl  
 Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.  
  
```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку для создания элемента управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, например «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылку на активный документ, таких как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML настроек\<текст настроек это строка текста\</BODY настроек \< /HTML настроек»  
  
    > [!NOTE]
    >  «MSHTML: «должен предшествовать фрагмент HTML, чтобы он обозначается как поток MSHTML. В системах Windows Mobile поддерживаются только идентификаторы ProgID и CLSID. Windows CE внедрять платформ, отличных от Windows Mobile с поддержкой CE IE поддержка всех типов, включая идентификатор ProgID, CLSID, URL-адрес, ссылка на активный документ и фрагмент кода HTML.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `dwResID`  
 Идентификатор ресурса для ресурса HTML. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если используется второй версии этого метода, элемент управления HTML создается и привязан к ресурсу, определяемому `dwResID`.  
  
 Этот метод дает тот же результат, что и вызов метода:  
  
 [!code-cpp[NVC_ATL_Windowing&#42;](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 В разделе [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) для создания, инициализации и лицензированного элемента управления ActiveX.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CreateControl`.  
  
##  <a name="createcontrolex"></a>CAxWindow::CreateControlEx  
 Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.  
  
```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку для создания элемента управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, например «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылку на активный документ, таких как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML настроек\<текст настроек это строка текста\</BODY настроек \< /HTML настроек»  
  
    > [!NOTE]
    >  «MSHTML: «должен предшествовать фрагмент HTML, чтобы он обозначается как поток MSHTML. В системах Windows Mobile поддерживаются только идентификаторы ProgID и CLSID. Windows CE внедрять платформ, отличных от Windows Mobile с поддержкой CE IE поддержка всех типов, включая идентификатор ProgID, CLSID, URL-адрес, ссылка на активный документ и фрагмент кода HTML.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `ppUnkControl`  
 [out] Адрес указателя, который получит **IUnknown** элемента управления. Может быть **NULL**.  
  
 `iidSink`  
 [in] Идентификатор исходящего интерфейса содержащегося объекта. Может быть **равным IID_NULL**.  
  
 *punkSink*  
 [in] Указатель на **IUnknown** интерфейс приемника объекта должен быть подключен к точке соединения для содержащегося объекта, заданного параметром `iidSink`.  
  
 `dwResID`  
 [in] Идентификатор ресурса для ресурса HTML. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CAxWindow::CreateControl](#createcontrol), но в отличие от этого метода `CreateControlEx` также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
 В разделе [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) для создания, инициализации и лицензированного элемента управления ActiveX.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CreateControlEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow::GetWndClassName  
 Получает имя класса окна.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, содержащую имя класса окна, nonlicensed элементов управления ActiveX.  
  
##  <a name="operator_eq"></a>CAxWindow::operator =  
 Назначает `HWND` к существующему `CAxWindow` объекта.  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 Дескриптор к существующему окну.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на текущий объект `CAxWindow`.  
  
##  <a name="querycontrol"></a>CAxWindow::QueryControl  
 Извлекает указанный интерфейс размещенного элемента управления.  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Указывает идентификатор IID интерфейса элемента управления.  
  
 `ppUnk`  
 [out] Указатель интерфейса элемента управления. В шаблоне версию этого метода нет необходимости для идентификатора ссылки при условии, что передается типизированный интерфейс с связанные UUID.  
  
 `Q`  
 [in] Интерфейс, запрашиваемый для.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="queryhost"></a>CAxWindow::QueryHost  
 Возвращает указанный интерфейс узла.  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Указывает идентификатор IID интерфейса элемента управления.  
  
 `ppUnk`  
 [out] Указатель интерфейса на узле. В шаблоне версию этого метода нет необходимости для идентификатора ссылки при условии, что передается типизированный интерфейс с связанные UUID.  
  
 `Q`  
 [in] Интерфейс, запрашиваемый для.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Интерфейс узла позволяет доступ к базовой функциональности кода размещения окна, реализуемый **AxWin**.  
  
##  <a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch  
 Задает интерфейс для внешних диспетчеризации `CAxWindow` объекта.  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 [in] Указатель на `IDispatch` интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler  
 Задает внешние [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для `CAxWindow` объекта.  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>Параметры  
 *pUIHandler*  
 [in] Указатель на **IDocHostUIHandlerDispatch** интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Внешние `IDocHostUIHandlerDispatch` интерфейс используется элементами управления, запрос узла для `IDocHostUIHandlerDispatch` интерфейса. Элемент управления WebBrowser является один элемент управления, который делает это.  
  
## <a name="see-also"></a>См. также  
 [Образец ATLCON](../../visual-cpp-samples.md)   
 [Класс CWindow](../../atl/reference/cwindow-class.md)   
 [Основы составного элемента управления](../../atl/atl-composite-control-fundamentals.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)


