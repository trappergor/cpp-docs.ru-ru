---
title: "Класс CAxWindow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
dev_langs: C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8848e8ecf85b073032561e2db52a0db1889911e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="caxwindow-class"></a>Класс CAxWindow
Этот класс предоставляет методы для работы с окном размещения элемента управления ActiveX.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Прикрепляет элемент ActiveX для `CAxWindow` объекта.|  
|[CAxWindow](#caxwindow)|Создает объект `CAxWindow`.|  
|[CreateControl](#createcontrol)|Создает элемент управления ActiveX, инициализирует его и размещает в `CAxWindow` окна.|  
|[CreateControlEx](#createcontrolex)|Создает элемент управления ActiveX и возвращает указатель интерфейса (или указатели) из элемента управления.|  
|[GetWndClassName](#getwndclassname)|(Статический) Извлекает имя класса стандартные `CAxWindow` объекта.|  
|[QueryControl](#querycontrol)|Извлекает **IUnknown** размещенного элемента управления ActiveX.|  
|[QueryHost](#queryhost)|Извлекает **IUnknown** указатель `CAxWindow` объекта.|  
|[SetExternalDispatch](#setexternaldispatch)|Задает интерфейс внешнего диспетчеризации, используемые `CAxWindow` объекта.|  
|[SetExternalUIHandler](#setexternaluihandler)|Задает внешний **IDocHostUIHandler** интерфейс, используемый `CAxWindow` объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Назначает **HWND** к существующему **CAxWindow** объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для управления окна, на котором размещается элемент управления ActiveX. Обеспечивается размещения» **AtlAxWin80»**, который является оболочкой для `CAxWindow`.  
  
 Класс `CAxWindow` реализуется в виде специализацией `CAxWindowT` класса. Такая специализация объявляется как:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Если вам нужно изменить базовый класс, можно использовать `CAxWindowT` и укажите новый базовый класс в качестве аргумента шаблона.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="attachcontrol"></a>CAxWindow::AttachControl  
 Создает новый объект узла, если он уже не существуют и прикрепляет к узлу указанного элемента управления.  
  
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
 Присоединяемый объект элемента управления необходимо правильно инициализировать перед вызовом `AttachControl`.  
  
##  <a name="caxwindow"></a>CAxWindow::CAxWindow  
 Создает `CAxWindow` с помощью существующего объекта дескриптора окна.  
  
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
  
-   ProgID, такие как «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылка для активного документа, такие как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY > \< /HTML >»  
  
    > [!NOTE]
    >  «MSHTML:» должен предшествовать фрагмент HTML, чтобы он назначен как поток MSHTML. Идентификаторы ProgID и CLSID, поддерживаются в системах Windows Mobile. Windows CE внедренные платформ, отличных от Windows Mobile с поддержкой CE IE поддержки всех типов, включая идентификатор ProgID, CLSID, URL-адрес, ссылка на активный документ и фрагмент кода HTML.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `dwResID`  
 Идентификатор ресурса HTML-ресурса. Элемент управления WebBrowser будет создана и загружен с указанным ресурсом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если используется вторая версия данного метода, HTML-элемент управления создается и привязан к ресурсу, определяемому `dwResID`.  
  
 Этот метод дает тот же результат, что и вызов метода:  
  
 [!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 В разделе [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) для создания, инициализации и размещения лицензированный элемент управления ActiveX.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CreateControl`.  
  
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
  
-   ProgID, такие как «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылка для активного документа, такие как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY > \< /HTML >»  
  
    > [!NOTE]
    >  «MSHTML:» должен предшествовать фрагмент HTML, чтобы он назначен как поток MSHTML. Идентификаторы ProgID и CLSID, поддерживаются в системах Windows Mobile. Windows CE внедренные платформ, отличных от Windows Mobile с поддержкой CE IE поддержки всех типов, включая идентификатор ProgID, CLSID, URL-адрес, ссылка на активный документ и фрагмент кода HTML.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `ppUnkControl`  
 [out] Адрес указателя, который получит **IUnknown** элемента управления. Может быть **NULL**.  
  
 `iidSink`  
 [in] Идентификатор исходящего интерфейса содержащегося объекта. Может быть **равным IID_NULL**.  
  
 *punkSink*  
 [in] Указатель на **IUnknown** интерфейса приемника объекта должны быть подключены к точкой соединения в автономной объекта, заданного параметром `iidSink`.  
  
 `dwResID`  
 [in] Идентификатор ресурса HTML-ресурса. Элемент управления WebBrowser будет создана и загружен с указанным ресурсом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CAxWindow::CreateControl](#createcontrol), но в отличие от этого метода `CreateControlEx` также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
 В разделе [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) для создания, инициализации и размещения лицензированный элемент управления ActiveX.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CreateControlEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow::GetWndClassName  
 Извлекает имя класса окна.  
  
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
 [out] Указатель интерфейса элемента управления. В версию шаблона этого метода нет необходимости для идентификатора ссылки, при условии, что передается интерфейс с связанного UUID.  
  
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
 [out] Указатель интерфейса на узле. В версию шаблона этого метода нет необходимости для идентификатора ссылки, при условии, что передается интерфейс с связанного UUID.  
  
 `Q`  
 [in] Интерфейс, запрашиваемый для.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Интерфейс узла разрешает доступ к базовой функции размещения окно кода, реализуемый **AxWin**.  
  
##  <a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch  
 Задает интерфейс диспетчеризации внешних `CAxWindow` объекта.  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 [in] Указатель на `IDispatch` интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler  
 Задает внешний [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для `CAxWindow` объекта.  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>Параметры  
 *pUIHandler*  
 [in] Указатель на **IDocHostUIHandlerDispatch** интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Внешние `IDocHostUIHandlerDispatch` интерфейс используется элементами управления, запрос узлу для `IDocHostUIHandlerDispatch` интерфейса. Элемент управления WebBrowser — один элемент управления, выполняющий это.  
  
## <a name="see-also"></a>См. также  
 [Образец ATLCON](../../visual-cpp-samples.md)   
 [Класс CWindow](../../atl/reference/cwindow-class.md)   
 [Принципы работы составного элемента управления](../../atl/atl-composite-control-fundamentals.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)

