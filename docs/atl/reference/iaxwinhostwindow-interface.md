---
title: "Интерфейс IAxWinHostWindow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28fdc1a3a26fc2bb6117c345da3588ff0d2de193
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="iaxwinhostwindow-interface"></a>Интерфейс IAxWinHostWindow
Этот интерфейс предоставляет методы для работы с элементом управления и его объект узла.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Присоединяет объект узла существующего элемента управления.|  
|[CreateControl](#createcontrol)|Создает элемент управления и прикрепляет его к объекту узла.|  
|[CreateControlEx](#createcontrolex)|Создает элемент управления и прикрепляет его к объекту узла при необходимости устанавливает обработчик события.|  
|[QueryControl](#querycontrol)|Возвращает указатель на интерфейс для размещенного элемента управления.|  
|[SetExternalDispatch](#setexternaldispatch)|Задает внешний `IDispatch` интерфейса.|  
|[SetExternalUIHandler](#setexternaluihandler)|Задает внешний `IDocHostUIHandlerDispatch` интерфейса.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляется элементом управления ActiveX ATL размещение объектов. Вызовите методы для этого интерфейса позволяет создать и назначить объект узла, для получения интерфейса из размещенного элемента управления или при размещении веб-браузер, задайте внешний disp-интерфейса и обработчик пользовательского интерфейса для использования элемента управления.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как IDL или C++, как показано ниже.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|См (также входит в состав ATLBase.h)|  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow::AttachControl  
 Прикрепляет элемент управления с существующие (и предварительно инициализированных) на базовый объект, с помощью окна, обозначенную `hWnd`.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkControl*  
 [in] Указатель на **IUnknown** интерфейса элемента управления для присоединения к объекту узла.  
  
 `hWnd`  
 [in] Дескриптор окна, используемое для размещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="createcontrol"></a>IAxWinHostWindow::CreateControl  
 Создает элемент управления, инициализирует его и размещает в окна, обозначенную `hWnd`.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 `lpTricsData`  
 [in] Строка, идентифицирующая элемент управления для создания. Может быть (включая фигурные) CLSID, ProgID, URL-адрес или исходный HTML-код (префиксом **MSHTML:**).  
  
 `hWnd`  
 [in] Дескриптор окна, используемое для размещения.  
  
 `pStream`  
 [in] Указатель интерфейса для поток, содержащий данные инициализации для элемента управления. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Это окно будет подклассом объектом узла, предоставление доступа к этот интерфейс, чтобы сообщения могут быть отражены в элемент управления и других функций контейнера будет работать.  
  
 Вызов этого метода эквивалентен вызову [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Создание лицензированный элемент управления ActiveX — [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
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
 [in] Строка, идентифицирующая элемент управления для создания. Может быть (включая фигурные) CLSID, ProgID, URL-адрес или необработанное HTML (с префиксом **MSHTML:**).  
  
 `hWnd`  
 [in] Дескриптор окна, используемое для размещения.  
  
 `pStream`  
 [in] Указатель интерфейса для поток, содержащий данные инициализации для элемента управления. Может быть **NULL**.  
  
 `ppUnk`  
 [out] Адрес указателя, который получит **IUnknown** интерфейса созданный элемент управления. Может быть **NULL**.  
  
 *riidAdvise*  
 [in] Идентификатор исходящего интерфейса содержащегося объекта. Может быть **равным IID_NULL**.  
  
 *punkAdvise*  
 [in] Указатель на **IUnknown** интерфейса приемника объекта должны быть подключены к точкой соединения в автономной объекта, заданного параметром `iidSink`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 В отличие от `CreateControl` метода `CreateControlEx` также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
 Создание лицензированный элемент управления ActiveX — [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Возвращает заданный указатель интерфейса, предоставляемые размещенного элемента управления.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `riid`  
 [in] Идентификатор элемента управления, запрашиваемый интерфейс.  
  
 `ppvObject`  
 [out] Адрес указателя, который получит указанный интерфейс созданный элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 Задает внешний disp-интерфейса, доступном через содержащиеся в нем элементы [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) метод.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 [in] Указатель на `IDispatch` интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 Вызовите эту функцию для задания внешних [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для `CAxWindow` объекта.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 [in] Указатель на **IDocHostUIHandlerDispatch** интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется элементами управления (например, элемент управления браузера), запрос узлу для `IDocHostUIHandlerDispatch` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









