---
title: "Интерфейс IAxWinHostWindow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- No header/ATL::IAxWinHostWindow
- No header/ATL::AttachControl
- No header/ATL::CreateControl
- No header/ATL::CreateControlEx
- No header/ATL::QueryControl
- No header/ATL::SetExternalDispatch
- No header/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e366e7e30e7b4080462fbc21c29b4ecdf0214ae
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindow-interface"></a>Интерфейс IAxWinHostWindow
Этот интерфейс предоставляет методы для работы с элементом управления и его объект узла.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Присоединяет существующего элемента управления к объекту главного приложения.|  
|[CreateControl](#createcontrol)|Создает элемент управления и присоединяет его к объекту главного приложения.|  
|[CreateControlEx](#createcontrolex)|Создает элемент управления, присоединяет его к объекту главного приложения и при необходимости устанавливает обработчик события.|  
|[QueryControl](#querycontrol)|Возвращает указатель на интерфейс для размещенного элемента управления.|  
|[SetExternalDispatch](#setexternaldispatch)|Задает внешние `IDispatch` интерфейса.|  
|[SetExternalUIHandler](#setexternaluihandler)|Задает внешние `IDocHostUIHandlerDispatch` интерфейса.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляется элементом управления ActiveX ATL размещение объектов. Вызовите методы на этот интерфейс, чтобы создать или присоединить элемент управления к объекту главного приложения для получения интерфейс размещенного элемента управления или для внешних диспетчерский или обработчик пользовательского интерфейса для использования при размещении веб-браузера.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как IDL или C++, как показано ниже.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Насколько (также входит в ATLBase.h)|  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow::AttachControl  
 Присоединяет существующего (и предварительно инициализированных) элемента управления к объекту главного приложения с помощью окна определяется `hWnd`.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkControl*  
 [in] Указатель на **IUnknown** интерфейса элемента управления должны быть присоединены к объект узла.  
  
 `hWnd`  
 [in] Дескриптор окна, используемый для размещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="createcontrol"></a>IAxWinHostWindow::CreateControl  
 Создает элемент управления, инициализирует его и размещает в окне, идентифицируемый `hWnd`.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 `lpTricsData`  
 [in] Строка, определяющая создаваемый элемент управления. Может быть (включая фигурные) CLSID, ProgID, URL-адрес или исходный HTML-код (с префиксом **MSHTML:**).  
  
 `hWnd`  
 [in] Дескриптор окна, используемый для размещения.  
  
 `pStream`  
 [in] Указатель на интерфейс для потока, содержащего данные инициализации для элемента управления. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Это окно будет подклассом объектом хоста, предоставление доступа к этот интерфейс, чтобы сообщения могут быть отражены в элемент управления и других функций контейнера будет работать.  
  
 Вызов этого метода эквивалентен вызову [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Создание лицензированный элемент управления ActiveX, в разделе [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx  
 Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне аналогично [IAxWinHostWindow::CreateControl](#createcontrol).  
  
```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 `lpTricsData`  
 [in] Строка, определяющая создаваемый элемент управления. Может быть (включая фигурные) CLSID, ProgID, URL-адрес или исходный HTML-код (с префиксом **MSHTML:**).  
  
 `hWnd`  
 [in] Дескриптор окна, используемый для размещения.  
  
 `pStream`  
 [in] Указатель на интерфейс для потока, содержащего данные инициализации для элемента управления. Может быть **NULL**.  
  
 `ppUnk`  
 [out] Адрес указателя, который получит **IUnknown** интерфейса созданный элемент управления. Может быть **NULL**.  
  
 *riidAdvise*  
 [in] Идентификатор исходящего интерфейса содержащегося объекта. Может быть **равным IID_NULL**.  
  
 *punkAdvise*  
 [in] Указатель на **IUnknown** интерфейс приемника объекта должен быть подключен к точке соединения для содержащегося объекта, заданного параметром `iidSink`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 В отличие от `CreateControl` метод `CreateControlEx` также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
 Создание лицензированный элемент управления ActiveX, в разделе [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Возвращает заданный указатель интерфейса предоставляемых размещенного элемента управления.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `riid`  
 [in] Идентификатор интерфейса запрашиваемого элемента управления.  
  
 `ppvObject`  
 [out] Адрес указателя, который получит указанный интерфейс созданный элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 Задает внешний disp-интерфейс, доступный в контейнере элементов управления через [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) метод.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 [in] Указатель на `IDispatch` интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 Вызовите эту функцию для задания внешние [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для `CAxWindow` объекта.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 [in] Указатель на **IDocHostUIHandlerDispatch** интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется элементами управления (например, элемент управления браузера), запрос узла для `IDocHostUIHandlerDispatch` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](http://msdn.microsoft.com/library/ad1f4f16-608d-4e96-8d30-04d4ca906a7b)










