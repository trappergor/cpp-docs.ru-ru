---
title: "Глобальные функции составного элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
dev_langs: C++
helpviewer_keywords: composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5a062ea9477df9db026c75bc775df804ed86da4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="composite-control-global-functions"></a>Глобальные функции составного элемента управления
Эти функции обеспечивают поддержку для создание диалоговых окон, а также для создания, размещения и лицензирование элементов управления ActiveX.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|Создает модальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. Появившемся окне может содержать элементы управления ActiveX.|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|Создает немодальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. Появившемся окне может содержать элементы управления ActiveX.|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Создает элемент управления ActiveX, инициализирует его, размещает в указанном окне и возвращает указатель интерфейса (или указатели) из элемента управления.|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, размещает в указанном окне и возвращает указатель интерфейса (или указатели) из элемента управления.|  
|[AtlAxAttachControl](#atlaxattachcontrol)|Присоединяет ранее созданный элемент управления к указанному окну.|  
|[AtlAxGetHost](#atlaxgethost)|Используется для получения прямой указатель интерфейса на контейнер для указанного окна (если таковые имеются), по его указателю.|  
|[AtlAxGetControl](#atlaxgetcontrol)|Используется для получения прямой указатель интерфейса для элемента управления, содержащегося в заданном окне (если таковые имеются), по его указателю.|  
|[AtlSetChildSite](#atlsetchildsite)|Инициализирует **IUnknown** дочернего сайта.|  
|[AtlAxWinInit](#atlaxwininit)|Инициализирует код размещения для AxWin объектов.|  
|[AtlAxWinTerm](#atlaxwinterm)|Отменяет инициализацию кода размещения для AxWin объектов.|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Возвращает сведения об интерфейсе источника по умолчанию объекта.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlhost.h  

##  <a name="atlaxdialogbox"></a>AtlAxDialogBox  
 Создает модальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем.  
   
```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 [in] Идентифицирует экземпляр модуля которого исполняемый файл содержит шаблон диалогового окна.  
  
 `lpTemplateName`  
 [in] Определяет шаблон диалогового окна. Этот параметр является либо указатель на завершающуюся значением null строка, указывающая имя шаблона диалоговых окон или целочисленное значение, указывающее идентификатор ресурса шаблона диалоговых окон. Если параметр задает идентификатор ресурса, его старшее слово должно быть равно нулю, и его младшее слово должно содержать идентификатор. Можно использовать [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) макрос для создания этого значения.  
  
 `hWndParent`  
 [in] Определяет, которому принадлежит данное диалоговое окно.  
  
 `lpDialogProc`  
 [in] Указывает процедуру диалогового окна. Дополнительные сведения о процедуру диалогового окна см. в разделе [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне **lParam** параметр **WM_INITDIALOG** сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Для использования **AtlAxDialogBox** с шаблона диалогового окна, который содержит элемент управления ActiveX, укажите допустимое **CLSID**, **APPID** или строку URL-адрес в качестве *текста* поле **УПРАВЛЕНИЯ** раздел ресурса диалогового окна, вместе с «AtlAxWin80» как *имя класса* поля в том же разделе. Следующий код демонстрирует какие допустимым **УПРАВЛЕНИЯ** может выглядеть раздела:  
  
```  
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,  
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100  
```  
  
 Дополнительные сведения о редактировании сценариев ресурсов см. в разделе [как: открытие файла описания ресурсов в текстовом формате](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Дополнительные сведения об операторах определения ресурса управления см. в разделе [общих параметров управления](http://msdn.microsoft.com/library/windows/desktop/aa380902) в Windows SDK*: средств SDK*.  
  
 Дополнительные сведения о диалоговых окнах Общие ссылки [следующейтаблице](http://msdn.microsoft.com/library/windows/desktop/ms645452) и [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) в Windows SDK.  
  
##  <a name="atlaxcreatedialog"></a>AtlAxCreateDialog  
 Создает немодальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем.  
  
```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 [in] Идентифицирует экземпляр модуля которого исполняемый файл содержит шаблон диалогового окна.  
  
 `lpTemplateName`  
 [in] Определяет шаблон диалогового окна. Этот параметр является либо указатель на завершающуюся значением null строка, указывающая имя шаблона диалоговых окон или целочисленное значение, указывающее идентификатор ресурса шаблона диалоговых окон. Если параметр задает идентификатор ресурса, его старшее слово должно быть равно нулю, и его младшее слово должно содержать идентификатор. Можно использовать [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) макрос для создания этого значения.  
  
 `hWndParent`  
 [in] Определяет, которому принадлежит данное диалоговое окно.  
  
 `lpDialogProc`  
 [in] Указывает процедуру диалогового окна. Дополнительные сведения о процедуру диалогового окна см. в разделе [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне **lParam** параметр **WM_INITDIALOG** сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Появившемся окне может содержать элементы управления ActiveX.  
  
 В разделе [CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434) и [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) в Windows SDK.  
  
##  <a name="atlaxcreatecontrol"></a>AtlAxCreateControl  
 Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.  
  

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку для передачи элемента управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, такие как «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылка для активного документа, такие как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY > \< /HTML >»  
  
    > [!NOTE]
    >  «MSHTML:» должен предшествовать фрагмент HTML, чтобы он назначен как поток MSHTML.  
  
 `hWnd`  
 [in] Дескриптор окна, будет вложен в элемент управления.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Это глобальная функция дает тот же результат, что и вызов метода [AtlAxCreateControlEx](#atlaxcreatecontrolex)( `lpszName` **,** `hWnd` **,** `pStream` **, NULL, NULL, NULL, NULL** );.  
  
 Создание лицензированный элемент управления ActiveX — [AtlAxCreateControlLic](#atlaxcreatecontrollic).  
  
##  <a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx  
 Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне. Можно также создать указатель интерфейса и приемник событий для нового элемента управления.  
  
```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку для передачи элемента управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, такие как «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылка для активного документа, такие как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY > \< /HTML >»  
  
    > [!NOTE]
    >  «MSHTML:» должен предшествовать фрагмент HTML, чтобы он назначен как поток MSHTML.  
  
 `hWnd`  
 [in] Дескриптор окна, будет вложен в элемент управления.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `ppUnkControl`  
 [out] Адрес указателя, который получит **IUnknown** созданного элемента управления. Может быть **NULL**.  
  
 `iidSink`  
 Идентификатор исходящего интерфейса содержащегося объекта.  
  
 *punkSink*  
 Указатель на **IUnknown** интерфейса приемника объекта должны быть подключены к точке подключения, заданной `iidSink` на содержащийся объект после успешного создания содержащегося объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `AtlAxCreateControlEx`Аналогично [AtlAxCreateControl](#atlaxcreatecontrol) , но также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
 Создание лицензированный элемент управления ActiveX — [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).  
  
##  <a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic  
 Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.  

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку для передачи элемента управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, такие как «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылка для активного документа, такие как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY > \< /HTML >»  
  
    > [!NOTE]
    >  «MSHTML:» должен предшествовать фрагмент HTML, чтобы он назначен как поток MSHTML.  
  
 `hWnd`  
 Дескриптор окна, будет вложен в элемент управления.  
  
 `pStream`  
 Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `bstrLic`  
 BSTR, содержащий лицензии для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) образец демонстрирует использование `AtlAxCreateControlLic`.  
  
##  <a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx  
 Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне. Можно также создать указатель интерфейса и приемник событий для нового элемента управления.  
  
```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку для передачи элемента управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, такие как «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылка для активного документа, такие как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY > \< /HTML >»  
  
    > [!NOTE]
    >  «MSHTML:» должен предшествовать фрагмент HTML, чтобы он назначен как поток MSHTML.  
  
 `hWnd`  
 Дескриптор окна, будет вложен в элемент управления.  
  
 `pStream`  
 Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `ppUnkControl`  
 [out] Адрес указателя, который получит **IUnknown** созданного элемента управления. Может быть **NULL**.  
  
 `iidSink`  
 Идентификатор исходящего интерфейса содержащегося объекта.  
  
 *punkSink*  
 Указатель на **IUnknown** интерфейса приемника объекта должны быть подключены к точке подключения, заданной `iidSink` на содержащийся объект после успешного создания содержащегося объекта.  
  
 `bstrLic`  
 BSTR, содержащий лицензии для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `AtlAxCreateControlLicEx`Аналогично [AtlAxCreateControlLic](#atlaxcreatecontrollic) , но также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) образец демонстрирует использование `AtlAxCreateControlLicEx`.  
  
##  <a name="atlaxattachcontrol"></a>AtlAxAttachControl  
 Присоединяет ранее созданный элемент управления к указанному окну.  
  
```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 [in] Указатель на **IUnknown** элемента управления.  
  
 `hWnd`  
 [in] Дескриптор окна, где будет размещаться элемент управления.  
  
 `ppUnkContainer`  
 [out] Указатель на указатель на **IUnknown** объекта-контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Используйте [AtlAxCreateControlEx](#atlaxcreatecontrolex) и [AtlAxCreateControl](#atlaxcreatecontrol) одновременно Создание и присоединение элемента управления.  
  
> [!NOTE]
>  Присоединяемый объект элемента управления необходимо правильно инициализировать перед вызовом `AtlAxAttachControl`.  
  
##  <a name="atlaxgethost"></a>AtlAxGetHost  
 Получает прямой указатель интерфейса на контейнер для указанного окна (если имеется) по его указателю.  
  
```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 [in] Дескриптор окна, в котором размещается элемент управления.  
  
 `pp`  
 [out] **IUnknown** контейнера элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="atlaxgetcontrol"></a>AtlAxGetControl  
 Получает прямой указатель интерфейса на элемент управления, который содержится в заданном окне (на основе его указателя).  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 [in] Дескриптор окна, в котором размещается элемент управления.  
  
 `pp`  
 [out] **IUnknown** размещаемого элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="atlsetchildsite"></a>AtlSetChildSite  
 Вызывайте эту функцию, чтобы задать для сайта дочернего объекта **IUnknown** родительского объекта.  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>Параметры  
 *punkChild*  
 [in] Указатель на **IUnknown** интерфейс дочернего элемента.  
  
 `punkParent`  
 [in] Указатель на **IUnknown** интерфейса родительского элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="atlaxwininit"></a>AtlAxWinInit  
 Эта функция инициализирует код размещения путем регистрации элемента управления ATL **«AtlAxWin80»** и **«AtlAxWinLic80»** классы окна, а также пару пользовательских сообщений окна.  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализацию кода размещения элемента управления был успешным; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию необходимо вызывать перед использованием элемента управления ATL, API размещения. После вызова этой функции **«AtlAxWin»** класс окна можно использовать в вызовах [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) или [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680), как описано в Windows SDK.  

##  <a name="atlaxwinterm"></a>AtlAxWinTerm  
 Эта функция отменяет инициализацию кода размещения, отменив регистрацию элемента управления ATL **«AtlAxWin80»** и **«AtlAxWinLic80»** классов окон.  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция просто вызывает [UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) как описано в Windows SDK.  
  
 Эта функция вызывается для очистки после уничтожения всех существующих окон узла Если вызван [AtlAxWinInit](#atlaxwininit) и больше не требуется создавать узла windows. Если не вызвать эту функцию, класс окна будет отменена автоматически при завершении процесса.  
  
##  <a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface  
 Вызывайте эту функцию для получения сведений об интерфейсе источника по умолчанию для объекта.  
  
```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```  
  
### <a name="parameters"></a>Параметры  
 `punkObj`  
 [in] Указатель на объект, для которого возвращаются сведения.  
  
 `plibid`  
 [out] Указатель на идентификатор LIBID библиотеки типов, содержащий определение исходного интерфейса.  
  
 `piid`  
 [out] Указатель на идентификатор интерфейса исходный интерфейс по умолчанию объекта.  
  
 *pdwMajor*  
 [out] Указатель на основной номер версии библиотеки типов, содержащий определение исходного интерфейса.  
  
 *pdwMinor*  
 [out] Указатель на дополнительный номер версии библиотеки типов, содержащий определение исходного интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `AtlGetObjectSourceInterface`можно предоставить с ИД интерфейса исходный интерфейс по умолчанию, а также идентификатор LIBID и основные и дополнительные номера версии библиотеки типов, описывающие этот интерфейс.  
  
> [!NOTE]
>  Для этой функции для успешного получения необходимые данные, объект, представленный `punkObj` необходимо реализовать `IDispatch` (и возвращают сведения о типе через **IDispatch::GetTypeInfo**), а также он должен также реализации `IProvideClassInfo2` или `IPersist`. Сведения о типе для интерфейса источника должен быть в той же библиотеки типов, как сведения о типе `IDispatch`.  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как можно определить класс приемника событий `CEasySink`, которое уменьшает число аргументов шаблона, которые можно передать в `IDispEventImpl` для самые необходимые. `EasyAdvise`и `EasyUnadvise` использовать `AtlGetObjectSourceInterface` для инициализации [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) члены перед вызовом [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) или [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).  
  
 [!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы для работы с составными элементами управления](../../atl/reference/composite-control-macros.md)
