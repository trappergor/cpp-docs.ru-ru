---
title: Интерфейс IAxWinHostWindow | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfafe3c59b8b36e95441c7fe269239d7f87111e7
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885858"
---
# <a name="iaxwinhostwindow-interface"></a>Интерфейс IAxWinHostWindow
Этот интерфейс содержит методы для работы элемента управления и его объект узла.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Присоединяет объект узла существующего элемента управления.|  
|[CreateControl](#createcontrol)|Создает элемент управления и прикрепляет его к объекту узла.|  
|[CreateControlEx](#createcontrolex)|Создает элемент управления и прикрепляет его к объекту узла при необходимости устанавливает обработчик события.|  
|[QueryControl](#querycontrol)|Возвращает указатель интерфейса для размещаемого элемента управления.|  
|[SetExternalDispatch](#setexternaldispatch)|Задает внешние `IDispatch` интерфейс.|  
|[SetExternalUIHandler](#setexternaluihandler)|Задает внешние `IDocHostUIHandlerDispatch` интерфейс.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляется элементом управления ActiveX библиотеки ATL, размещение объектов. Вызовите методы на этом интерфейсе, чтобы создать и/или подключить элемент управления на базовый объект, чтобы получить интерфейс из размещаемого элемента управления или установить внешние disp-интерфейс или обработчик пользовательского интерфейса для использования при размещении веб-браузера.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как файл IDL или C++, как показано ниже.  
  
|Тип определения|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Насколько (также входит в ATLBase.h)|  
  
##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl  
 Прикрепляет элемент существующего (и предварительно инициализированных) в объект узла, с помощью окна определяется *hWnd*.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkControl*  
 [in] Указатель на `IUnknown` интерфейса элемента управления должны быть присоединены к объекта узла.  
  
 *hWnd*  
 [in] Дескриптор окна, используемый для размещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl  
 Создает элемент управления, инициализирует его и размещает его в окне, идентифицируемый *hWnd*.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 *lpTricsData*  
 [in] Строка, определяющая элемент управления для создания. Может быть (необходимо использовать фигурные скобки) CLSID, ProgID, URL-адрес или необработанное HTML (с префиксом **MSHTML:**).  
  
 *hWnd*  
 [in] Дескриптор окна, используемый для размещения.  
  
 *pStream*  
 [in] Указатель на интерфейс для поток, содержащий данные инициализации для элемента управления. Может иметь значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Это окно будет разделяться на подклассы объектом узла, предоставляя этот интерфейс, чтобы сообщения могут быть отражены в элемент управления и другие функции контейнеров будут работать.  
  
 Вызов этого метода эквивалентен вызову [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Чтобы создать лицензированный элемент управления ActiveX, см. в разделе [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx  
 Создает элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [IAxWinHostWindow::CreateControl](#createcontrol).  
  
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
 *lpTricsData*  
 [in] Строка, определяющая элемент управления для создания. Может быть (необходимо использовать фигурные скобки) CLSID, ProgID, URL-адрес или необработанное HTML (с префиксом **MSHTML:**).  
  
 *hWnd*  
 [in] Дескриптор окна, используемый для размещения.  
  
 *pStream*  
 [in] Указатель на интерфейс для поток, содержащий данные инициализации для элемента управления. Может иметь значение NULL.  
  
 *ppUnk*  
 [out] Адрес указателя, который будет получать `IUnknown` интерфейса созданный элемент управления. Может иметь значение NULL.  
  
 *riidAdvise*  
 [in] Идентификатор исходящего интерфейса на содержащийся объект. Может быть IID_NULL.  
  
 *punkAdvise*  
 [in] Указатель на `IUnknown` интерфейс приемника объекта должен быть подключен к точкой соединения в автономной объекта, заданного параметром `iidSink`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 В отличие от `CreateControl` метода `CreateControlEx` также позволяет получать указатель интерфейса на вновь созданный элемент управления и настройка приемник событий для получения события, инициируемые элементом управления.  
  
 Чтобы создать лицензированный элемент управления ActiveX, см. в разделе [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl  
 Возвращает заданный указатель интерфейса, предоставляемые размещенного элемента управления.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 [in] Идентификатор интерфейса для запрашиваемого элемента управления.  
  
 *ppvObject*  
 [out] Адрес указателя, который получит указанный интерфейс созданный элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch  
 Задает внешний disp-интерфейс, который доступен на вложенные элементы управления через [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) метод.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 *pDisp*  
 [in] Указатель на `IDispatch` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler  
 Вызывайте эту функцию, чтобы задать внешний [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для `CAxWindow` объекта.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 *pDisp*  
 [in] Указатель на `IDocHostUIHandlerDispatch` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется элементами управления (например, элемент управления браузера), отправляющие запросы к узлу для `IDocHostUIHandlerDispatch` интерфейс.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









