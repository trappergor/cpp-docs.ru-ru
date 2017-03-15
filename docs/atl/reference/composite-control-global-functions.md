---
title: "Глобальные функции составной элемент управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: dd043335df32c04349403bbfe38e647f352826c4
ms.lasthandoff: 02/24/2017

---
# <a name="composite-control-global-functions"></a>Глобальные функции составного элемента управления
Эти функции обеспечивают поддержку для создания диалоговых окнах, а также для создания, размещения и лицензирование элементов управления ActiveX.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|Создает модальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. Открывшемся диалоговом окне может содержать элементы управления ActiveX.|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|Создает немодальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. Открывшемся диалоговом окне может содержать элементы управления ActiveX.|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Создает элемент управления ActiveX, инициализирует его, размещает в указанном окне и получает указатель на интерфейс (или указатели) с элементом управления.|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, размещает в указанном окне и получает указатель на интерфейс (или указатели) с элементом управления.|  
|[AtlAxAttachControl](#atlaxattachcontrol)|Присоединяет ранее созданный элемент управления к указанному окну.|  
|[AtlAxGetHost](#atlaxgethost)|Для получения прямой указатель интерфейса на контейнер для указанного окна (если таковые имеются) по его указателю.|  
|[AtlAxGetControl](#atlaxgetcontrol)|Для получения прямой указатель интерфейса на элемент управления, содержащихся в заданном окне (если таковые имеются), учитывая его дескриптор.|  
|[AtlSetChildSite](#atlsetchildsite)|Инициализирует **IUnknown** дочернего сайта.|  
|[AtlAxWinInit](#atlaxwininit)|Инициализирует код размещения для AxWin объектов.|  
|[AtlAxWinTerm](#atlaxwinterm)|Отменяет инициализацию кода размещения для AxWin объектов.|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Возвращает сведения об интерфейсе источника по умолчанию объекта.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlhost.h  

##  <a name="a-nameatlaxdialogboxa--atlaxdialogbox"></a><a name="atlaxdialogbox"></a>AtlAxDialogBox  
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
 [in] Определяет шаблон диалогового окна. Этот параметр является либо указатель на строку символом null, указывает имя шаблона поля диалогового окна или целочисленное значение, указывающее идентификатор ресурса шаблонов диалоговых окон. Если параметр указывает идентификатор ресурса, его старшее слово должно быть равно нулю, и его младшее слово должно содержать идентификатор. Можно использовать [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) макрос для создания этого значения.  
  
 `hWndParent`  
 [in] Определяет, которому принадлежит данное диалоговое окно.  
  
 `lpDialogProc`  
 [in] Указывает процедуру диалогового окна. Дополнительные сведения о процедура диалогового окна в разделе [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне **lParam** параметр **WM_INITDIALOG** сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Для использования **AtlAxDialogBox** с шаблона диалогового окна, содержащего элемент управления ActiveX, укажите допустимое **CLSID**, **APPID** или строку URL-адреса в качестве *текст* поле **УПРАВЛЕНИЯ** раздел ресурса диалогового окна, вместе с «AtlAxWin80» как *имя класса* поля в одном разделе. Следующий код демонстрирует, что является допустимым **УПРАВЛЕНИЯ** раздел может иметь следующий вид:  
  
 `CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,`  
  
 `"AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100`  
  
 Дополнительные сведения о редактировании ресурсов см. в разделе [Практическое руководство: открытие файла описания ресурсов в текстовом формате](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Дополнительные сведения об инструкциях определения ресурсов элемента управления в разделе [общих параметров управления](http://msdn.microsoft.com/library/windows/desktop/aa380902) под [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *: пакет инструментов SDK*.  
  
 Дополнительные сведения о диалоговых окнах в целом см. [DialogBox](http://msdn.microsoft.com/library/windows/desktop/ms645452) и [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameatlaxcreatedialoga--atlaxcreatedialog"></a><a name="atlaxcreatedialog"></a>AtlAxCreateDialog  
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
 [in] Определяет шаблон диалогового окна. Этот параметр является либо указатель на строку символом null, указывает имя шаблона поля диалогового окна или целочисленное значение, указывающее идентификатор ресурса шаблонов диалоговых окон. Если параметр указывает идентификатор ресурса, его старшее слово должно быть равно нулю, и его младшее слово должно содержать идентификатор. Можно использовать [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) макрос для создания этого значения.  
  
 `hWndParent`  
 [in] Определяет, которому принадлежит данное диалоговое окно.  
  
 `lpDialogProc`  
 [in] Указывает процедуру диалогового окна. Дополнительные сведения о процедура диалогового окна в разделе [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне **lParam** параметр **WM_INITDIALOG** сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Открывшемся диалоговом окне может содержать элементы управления ActiveX.  
  
 В разделе [CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434) и [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameatlaxcreatecontrola--atlaxcreatecontrol"></a><a name="atlaxcreatecontrol"></a>AtlAxCreateControl  
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
 Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, например «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылку на активный документ, таких как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML настроек\<текст настроек это строка текста\</BODY настроек \< /HTML настроек»  
  
    > [!NOTE]
    >  «MSHTML: «должен предшествовать фрагмент HTML, чтобы он обозначается как поток MSHTML.  
  
 `hWnd`  
 [in] Дескриптор окна, элемент управления будет назначена.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Это глобальная функция дает тот же результат, что и вызов метода [AtlAxCreateControlEx](#atlaxcreatecontrolex)( `lpszName` **,** `hWnd` **,** `pStream` **, NULL, NULL, NULL, NULL** );.  
  
 Создание лицензированный элемент управления ActiveX, в разделе [AtlAxCreateControlLic](#atlaxcreatecontrollic).  
  
##  <a name="a-nameatlaxcreatecontrolexa--atlaxcreatecontrolex"></a><a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx  
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
 Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, например «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылку на активный документ, таких как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML настроек\<текст настроек это строка текста\</BODY настроек \< /HTML настроек»  
  
    > [!NOTE]
    >  «MSHTML: «должен предшествовать фрагмент HTML, чтобы он обозначается как поток MSHTML.  
  
 `hWnd`  
 [in] Дескриптор окна, элемент управления будет назначена.  
  
 `pStream`  
 [in] Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 [out] Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `ppUnkControl`  
 [out] Адрес указателя, который получит **IUnknown** созданного элемента управления. Может быть **NULL**.  
  
 `iidSink`  
 Идентификатор исходящего интерфейса содержащегося объекта.  
  
 *punkSink*  
 Указатель на **IUnknown** интерфейс приемника объекта должен быть подключен к точке подключения, заданной `iidSink` на содержащийся объект после успешного создания содержащегося объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `AtlAxCreateControlEx`Аналогично [AtlAxCreateControl](#atlaxcreatecontrol) , но также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
 Создание лицензированный элемент управления ActiveX, в разделе [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).  
  
##  <a name="a-nameatlaxcreatecontrollica--atlaxcreatecontrollic"></a><a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic  
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
 Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, например «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылку на активный документ, таких как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML настроек\<текст настроек это строка текста\</BODY настроек \< /HTML настроек»  
  
    > [!NOTE]
    >  «MSHTML: «должен предшествовать фрагмент HTML, чтобы он обозначается как поток MSHTML.  
  
 `hWnd`  
 Дескриптор окна, элемент управления будет назначена.  
  
 `pStream`  
 Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `bstrLic`  
 BSTR, содержащий лицензии для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример использования `AtlAxCreateControlLic`.  
  
##  <a name="a-nameatlaxcreatecontrollicexa--atlaxcreatecontrollicex"></a><a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx  
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
 Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:  
  
-   ProgID, например «MSCAL. Calendar.7»  
  
-   CLSID, например «{8E27C92B-1264-101C-8A2F-040224009C02}»  
  
-   URL-адрес, например «http://www.microsoft.com»  
  
-   Ссылку на активный документ, таких как «file://\\\Documents\MyDoc.doc»  
  
-   Фрагмент HTML, такие как «MSHTML:\<HTML настроек\<текст настроек это строка текста\</BODY настроек \< /HTML настроек»  
  
    > [!NOTE]
    >  «MSHTML: «должен предшествовать фрагмент HTML, чтобы он обозначается как поток MSHTML.  
  
 `hWnd`  
 Дескриптор окна, элемент управления будет назначена.  
  
 `pStream`  
 Указатель на поток, который используется для инициализации свойств элемента управления. Может быть **NULL**.  
  
 `ppUnkContainer`  
 Адрес указателя, который получит **IUnknown** контейнера. Может быть **NULL**.  
  
 `ppUnkControl`  
 [out] Адрес указателя, который получит **IUnknown** созданного элемента управления. Может быть **NULL**.  
  
 `iidSink`  
 Идентификатор исходящего интерфейса содержащегося объекта.  
  
 *punkSink*  
 Указатель на **IUnknown** интерфейс приемника объекта должен быть подключен к точке подключения, заданной `iidSink` на содержащийся объект после успешного создания содержащегося объекта.  
  
 `bstrLic`  
 BSTR, содержащий лицензии для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `AtlAxCreateControlLicEx`Аналогично [AtlAxCreateControlLic](#atlaxcreatecontrollic) , но также позволяет получать указатель интерфейса на вновь созданного элемента управления и настроить приемник событий для получения событий, произошедших в элементе управления.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример использования `AtlAxCreateControlLicEx`.  
  
##  <a name="a-nameatlaxattachcontrola--atlaxattachcontrol"></a><a name="atlaxattachcontrol"></a>AtlAxAttachControl  
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
 [in] Дескриптор окна, в котором будет размещен элемент управления.  
  
 `ppUnkContainer`  
 [out] Указатель на указатель на **IUnknown** объекта-контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Используйте [AtlAxCreateControlEx](#atlaxcreatecontrolex) и [AtlAxCreateControl](#atlaxcreatecontrol) как одновременно создать и подключить элемент управления.  
  
> [!NOTE]
>  Присоединяемый объект управления необходимо правильно инициализировать перед вызовом метода `AtlAxAttachControl`.  
  
##  <a name="a-nameatlaxgethosta--atlaxgethost"></a><a name="atlaxgethost"></a>AtlAxGetHost  
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
  
##  <a name="a-nameatlaxgetcontrola--atlaxgetcontrol"></a><a name="atlaxgetcontrol"></a>AtlAxGetControl  
 Получает прямой указатель интерфейса на элемент управления, который содержится в заданном окне (на основе его указателя).  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 [in] Дескриптор окна, в котором размещается элемент управления.  
  
 `pp`  
 [out] **IUnknown** , размещенного элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="a-nameatlsetchildsitea--atlsetchildsite"></a><a name="atlsetchildsite"></a>AtlSetChildSite  
 Эта функция вызывается для сайта дочернего объекта, чтобы задать **IUnknown** родительского объекта.  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>Параметры  
 *punkChild*  
 [in] Указатель на **IUnknown** интерфейс дочернего элемента.  
  
 `punkParent`  
 [in] Указатель на **IUnknown** интерфейс родительского объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="a-nameatlaxwininita--atlaxwininit"></a><a name="atlaxwininit"></a>AtlAxWinInit  
 Эта функция инициализирует код размещения путем регистрации элемента управления ATL **«AtlAxWin80»** и **«AtlAxWinLic80»** классы окна, а также пару пользовательских сообщений окна.  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация код размещения элемента управления прошла успешно; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должен вызываться перед использованием элемента управления ATL, API размещения. После вызова этой функции **«AtlAxWin»** класс окна можно использовать в вызовах [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) или [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  

##  <a name="a-nameatlaxwinterma--atlaxwinterm"></a><a name="atlaxwinterm"></a>AtlAxWinTerm  
 Эта функция отменяет инициализацию кода размещения, отменив регистрацию элемента управления ATL **«AtlAxWin80»** и **«AtlAxWinLic80»** классы окон.  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция просто вызывает [UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Эта функция вызывается для очистки после всех существующих узлов windows были уничтожены при вызове [AtlAxWinInit](#atlaxwininit) и больше не требуется создавать узла windows. Если не вызвать эту функцию, класс окна будет отменена автоматически при завершении процесса.  
  
##  <a name="a-nameatlgetobjectsourceinterfacea--atlgetobjectsourceinterface"></a><a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface  
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
 [out] Указатель на идентификатор интерфейса объекта по умолчанию исходного интерфейса.  
  
 *pdwMajor*  
 [out] Указатель на основной номер версии библиотеки типов, содержащий определение исходного интерфейса.  
  
 *pdwMinor*  
 [out] Указатель на дополнительный номер версии библиотеки типов, содержащий определение исходного интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `AtlGetObjectSourceInterface`можно предоставить вам с Идентификатором интерфейса интерфейсе источника по умолчанию, а также идентификатор LIBID и основные и дополнительные номера версий библиотеки типов, описывающие этот интерфейс.  
  
> [!NOTE]
>  Эта функция для успешного получения запрошенных сведений объект, представленный `punkObj` необходимо реализовать `IDispatch` (и возвращают сведения о типе через **IDispatch::GetTypeInfo**), а также он должен также реализовывать либо `IProvideClassInfo2` или `IPersist`. Сведения о типе для исходного интерфейса должен быть в той же библиотеки типов, как сведения о типе `IDispatch`.  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как можно определить класс приемника событий `CEasySink`, уменьшает количество аргументов шаблона, которые можно передать `IDispEventImpl` на самые необходимые. `EasyAdvise`и `EasyUnadvise` использовать `AtlGetObjectSourceInterface` для инициализации [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) члены перед вызовом метода [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) или [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).  
  
 [!code-cpp[NVC_ATL_Windowing&#93;](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы в составной элемент управления](../../atl/reference/composite-control-macros.md)

