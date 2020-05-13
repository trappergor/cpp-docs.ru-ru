---
title: Композитные контрольные глобальные функции
ms.date: 11/04/2016
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
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
ms.openlocfilehash: 99ecd4cf04b3eb696f897d6ef5a5e3839d46ef17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331601"
---
# <a name="composite-control-global-functions"></a>Композитные контрольные глобальные функции

Эти функции обеспечивают поддержку для создания диалоговых коробок, а также для создания, хостинга и лицензирования управления ActiveX.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|Создает модальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. В результате диалоговая коробка может содержать элементы управления ActiveX.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|Создает немодальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. В результате диалоговая коробка может содержать элементы управления ActiveX.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Создает элемент управления ActiveX, инициализирует его, размещает его в указанном окне и извлекает указатель интерфейса (или указателей) из элемента управления.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, размещает его в указанном окне и извлекает указатель интерфейса (или указателей) из элемента управления.|
|[AtlAxAttachControl](#atlaxattachcontrol)|Присоединяет ранее созданный элемент управления к указанному окну.|
|[AtlAxGetHost](#atlaxgethost)|Используется для получения указателя прямого интерфейса к контейнеру для указанного окна (если таковые имеется), учитывая его ручку.|
|[AtlAxGetControl](#atlaxgetcontrol)|Используется для получения прямого указателя интерфейса на элемент управления, содержащегося внутри указанного окна (если таковые имеется), учитывая его ручку.|
|[AtlSetChildSite](#atlsetchildsite)|Инициализирует `IUnknown` сайт для детей.|
|[AtlAxWinInit](#atlaxwininit)|Инициализирует код хостинга для объектов AxWin.|
|[AtlAxWinTerm](#atlaxwinterm)|Не инициирует код хостинга для объектов AxWin.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Возвращает информацию об интерфейсе источника по умолчанию объекта.|

## <a name="requirements"></a>Требования

**Заголовок:** atlhost.h

## <a name="atlaxdialogbox"></a><a name="atlaxdialogbox"></a>AtlAxDialogBox

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

*hInstance*<br/>
(в) Идентифицирует экземпляр модуля, исполняемый файл которого содержит шаблон диалогового окна.

*lpTemplateName*<br/>
(в) Идентифицирует шаблон диалогового окна. Этот параметр является либо указателем на строку символов с нулевым завершением, которая определяет название шаблона диалогового окна, либо значение мгновенных, определяющее идентификатор ресурса шаблона диалогового окна. Если параметр определяет идентификатор ресурса, его слово высокого порядка должно быть нулевым, а его слово низкого порядка должно содержать идентификатор. Для создания этого значения можно использовать макрос [MAKEINTRESOURCE.](/windows/win32/api/winuser/nf-winuser-makeintresourcew)

*hWndParent*<br/>
(в) Идентифицирует окно, которому принадлежит диалоговая коробка.

*lpDialogProc*<br/>
(в) Указывает на процедуру диалогового окна. Для получения дополнительной информации о процедуре диалогового окна, [см.](/windows/win32/api/winuser/nc-winuser-dlgproc)

*dwInitParam*<br/>
(в) Определяет значение для передачи в поле диалога в параметре *lParam* WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Для `AtlAxDialogBox` использования шаблона диалогов, содержащего элемент управления ActiveX, укажите действительную строку CLSID, APPID или URL в виде *текстового* поля раздела **CONTROL** ресурса диалогов, а также "AtlAxWin80" в качестве поля *имени класса* под тем же разделом. Ниже показано, как может выглядеть допустимый раздел **CONTROL:**

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

Для получения дополнительной информации о редактировании сценариев ресурсов [см.](../../windows/how-to-open-a-resource-script-file-in-text-format.md) Для получения дополнительной информации о [Common Control Parameters](/windows/win32/menurc/common-control-parameters) инструкциях по определению ресурсов управления см.

Для получения дополнительной информации о диалоговых яках в целом, обратитесь к [DialogBox](/windows/win32/api/winuser/nf-winuser-dialogboxw) и [CreateDialogParam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) в Windows SDK.

## <a name="atlaxcreatedialog"></a><a name="atlaxcreatedialog"></a>AtlAxCreateДиалог

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

*hInstance*<br/>
(в) Идентифицирует экземпляр модуля, исполняемый файл которого содержит шаблон диалогового окна.

*lpTemplateName*<br/>
(в) Идентифицирует шаблон диалогового окна. Этот параметр является либо указателем на строку символов с нулевым завершением, которая определяет название шаблона диалогового окна, либо значение мгновенных, определяющее идентификатор ресурса шаблона диалогового окна. Если параметр определяет идентификатор ресурса, его слово высокого порядка должно быть нулевым, а его слово низкого порядка должно содержать идентификатор. Для создания этого значения можно использовать макрос [MAKEINTRESOURCE.](/windows/win32/api/winuser/nf-winuser-makeintresourcew)

*hWndParent*<br/>
(в) Идентифицирует окно, которому принадлежит диалоговая коробка.

*lpDialogProc*<br/>
(в) Указывает на процедуру диалогового окна. Для получения дополнительной информации о процедуре диалогового окна, [см.](/windows/win32/api/winuser/nc-winuser-dlgproc)

*dwInitParam*<br/>
(в) Определяет значение для передачи в поле диалога в параметре *lParam* WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

В результате диалоговая коробка может содержать элементы управления ActiveX.

Смотрите [CreateDialog](/windows/win32/api/winuser/nf-winuser-createdialogw) и [CreateDialogParam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) в SDK Windows.

## <a name="atlaxcreatecontrol"></a><a name="atlaxcreatecontrol"></a>AtlAxCreateControl

Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, которая должна быть передана в управление. Должен быть отформатирован одним из следующих способов:

- Прогид, например,`"MSCAL.Calendar.7"`

- CLSID, такие как`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL, такой как`"<https://www.microsoft.com>"`

- Ссылка на активный документ, такой как`"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML, например,`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML.

*Hwnd*<br/>
(в) Ручка к окну, к которым будет прикреплен элемент управления.

*pStream*<br/>
(в) Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
(ваут) Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Эта глобальная функция дает вам тот же результат, что и вызов [AtlAxCreateControlEx](#atlaxcreatecontrolex)*(lpszName,* *hWnd,* *pStream*, NULL, NULL, NULL, NULL);.

Чтобы создать лицензированный элемент управления [AtlAxCreateControlLic](#atlaxcreatecontrollic)ActiveX, см.

## <a name="atlaxcreatecontrolex"></a><a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx

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

*lpszName*<br/>
Указатель на строку, которая должна быть передана в управление. Должен быть отформатирован одним из следующих способов:

- Прогид, например,`"MSCAL.Calendar.7"`

- CLSID, такие как`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL, такой как`"<https://www.microsoft.com>"`

- Ссылка на активный документ, такой как`"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML, например,`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML.

*Hwnd*<br/>
(в) Ручка к окну, к которым будет прикреплен элемент управления.

*pStream*<br/>
(в) Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
(ваут) Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

*ppUnkControl*<br/>
(ваут) Адрес указателя, который получит `IUnknown` созданный элемент управления. Может иметь значение NULL.

*iidSink*<br/>
Идентификатор интерфейса исходящего интерфейса на содержащемся объекте.

*punkSink*<br/>
Указатель на `IUnknown` интерфейс объекта раковины, который будет подключен к точке соединения, указанной *iidSink* на содержащемся объекте после успешного создания содержащегося объекта.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

`AtlAxCreateControlEx`похож на [AtlAxCreateControl,](#atlaxcreatecontrol) но также позволяет получить указатель интерфейса к вновь созданному элементу управления и настроить раковину события для получения событий, выпущенных элементом управления.

Чтобы создать лицензированный элемент управления [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)ActiveX, см.

## <a name="atlaxcreatecontrollic"></a><a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic

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

*lpszName*<br/>
Указатель на строку, которая должна быть передана в управление. Должен быть отформатирован одним из следующих способов:

- Прогид, например,`"MSCAL.Calendar.7"`

- CLSID, такие как`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL, такой как`"<https://www.microsoft.com>"`

- Ссылка на активный документ, такой как`"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML, например,`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML.

*Hwnd*<br/>
Ручка к окну, к которым будет прикреплен элемент управления.

*pStream*<br/>
Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

*bstrLic*<br/>
BSTR, содержащий лицензию на управление.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца того, как использовать `AtlAxCreateControlLic`.

## <a name="atlaxcreatecontrollicex"></a><a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx

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

*lpszName*<br/>
Указатель на строку, которая должна быть передана в управление. Должен быть отформатирован одним из следующих способов:

- Прогид, например,`"MSCAL.Calendar.7"`

- CLSID, такие как`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL, такой как`"<https://www.microsoft.com>"`

- Ссылка на активный документ, такой как`"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML, например,`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML.

*Hwnd*<br/>
Ручка к окну, к которым будет прикреплен элемент управления.

*pStream*<br/>
Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

*ppUnkControl*<br/>
(ваут) Адрес указателя, который получит `IUnknown` созданный элемент управления. Может иметь значение NULL.

*iidSink*<br/>
Идентификатор интерфейса исходящего интерфейса на содержащемся объекте.

*punkSink*<br/>
Указатель на `IUnknown` интерфейс объекта раковины, который будет подключен к точке соединения, указанной *iidSink* на содержащемся объекте после успешного создания содержащегося объекта.

*bstrLic*<br/>
BSTR, содержащий лицензию на управление.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

`AtlAxCreateControlLicEx`похож на [AtlAxCreateControlLic,](#atlaxcreatecontrollic) но также позволяет получить указатель интерфейса к вновь созданному элементу управления и настроить раковину события для получения событий, выпущенных элементом управления.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца того, как использовать `AtlAxCreateControlLicEx`.

## <a name="atlaxattachcontrol"></a><a name="atlaxattachcontrol"></a>AtlAxAttachControl

Присоединяет ранее созданный элемент управления к указанному окну.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
(в) Указатель на `IUnknown` элемент управления.

*Hwnd*<br/>
(в) Ручка к окну, которая будет размещать элемент управления.

*ppUnkContainer*<br/>
(ваут) Указатель указателя на указатель `IUnknown` на контейнерный объект.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Используйте [AtlAxCreateControlEx](#atlaxcreatecontrolex) и [AtlAxCreateControl](#atlaxcreatecontrol) для одновременного создания и присоединения элемента управления.

> [!NOTE]
> Присоединенный объект управления должен быть правильно `AtlAxAttachControl`инициализирован перед вызовом.

## <a name="atlaxgethost"></a><a name="atlaxgethost"></a>AtlAxGetHost

Получает прямой указатель интерфейса на контейнер для указанного окна (если имеется) по его указателю.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Параметры

*H*<br/>
(в) Ручка к окну, которая размещает элемент управления.

*Pp*<br/>
(ваут) Контейнер `IUnknown` управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="atlaxgetcontrol"></a><a name="atlaxgetcontrol"></a>AtlAxGetControl

Получает прямой указатель интерфейса на элемент управления, который содержится в заданном окне (на основе его указателя).

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Параметры

*H*<br/>
(в) Ручка к окну, которая размещает элемент управления.

*Pp*<br/>
(ваут) Контроль `IUnknown` размещается.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="atlsetchildsite"></a><a name="atlsetchildsite"></a>AtlSetChildSite

Вызовите эту функцию, чтобы установить участок объекта ребенка к `IUnknown` родительскому объекту.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>Параметры

*punkChild*<br/>
(в) Указатель на `IUnknown` интерфейс ребенка.

*панкРодитель*<br/>
(в) Указатель на `IUnknown` интерфейс родительского интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="atlaxwininit"></a><a name="atlaxwininit"></a>АтлаксВинит

Эта функция инициализирует код управления atL хостинга, регистрируя **"AtlAxWin80"** и **"AtlAxWinLic80"** окна классов плюс несколько пользовательских сообщений окна.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если инициализация кода хостинга управления была успешной; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Эта функция должна быть вызвана перед использованием API управления ATL. После вызова этой функции, класс окон **"AtlAxWin"** может быть использован в вызовах [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) или [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw), как описано в SDK Windows.

## <a name="atlaxwinterm"></a><a name="atlaxwinterm"></a>AtlAxWinTerm

Эта функция неинициализирует код управления atL хостинга путем unregistering **"AtlAxWin80"** и **"AtlAxWinLic80"** оконные классы.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается TRUE.

### <a name="remarks"></a>Remarks

Эта функция просто вызывает [UnregisterClass,](/windows/win32/api/winuser/nf-winuser-unregisterclassw) как описано в Windows SDK.

Вызовите эту функцию для очистки после того, как все существующие окна хоста были уничтожены, если вы позвонили [в AtlAxWinInit](#atlaxwininit) и вам больше не нужно создавать окна хоста. Если вы не вызовете эту функцию, класс окон будет автоматически незарегистрирован, когда процесс завершается.

## <a name="atlgetobjectsourceinterface"></a><a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface

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

*панкОбж*<br/>
(в) Указатель на объект, для которого информация должна быть возвращена.

*плибид*<br/>
(ваут) Указатель на LIBID библиотеки типов, содержащий определение исходного интерфейса.

*пиид*<br/>
(ваут) Указатель на идентификатор интерфейса исходного интерфейса объекта по умолчанию.

*pdwMajor*<br/>
(ваут) Указатель на основной номер версии библиотеки типов, содержащий определение исходного интерфейса.

*pdwMinor*<br/>
(ваут) Указатель на номер незначительной версии библиотеки типов, содержащий определение исходного интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

`AtlGetObjectSourceInterface`может предоставить вам идентификатор интерфейса исходного интерфейса по умолчанию, а также LIBID и основные и незначительные номера версий библиотеки типов, описывающие этот интерфейс.

> [!NOTE]
> Для того чтобы эта функция успешно получила запрашиваемую информацию, `IDispatch` объект, представленный `IDispatch::GetTypeInfo` *punkObj,* должен `IProvideClassInfo2` реализовать `IPersist`(и вернуть информацию типа через) плюс он также должен реализовать либо или . Информация типа для исходного интерфейса должна находиться в `IDispatch`той же библиотеке типа, что и информация типа для.

### <a name="example"></a>Пример

Приведенный ниже пример показывает, как можно `CEasySink`определить класс раковины события, что уменьшает `IDispEventImpl` количество аргументов шаблона, которые можно перейти к голым основам. `EasyAdvise`и `EasyUnadvise` `AtlGetObjectSourceInterface` использовать для инициализации [iDispEventImpl](../../atl/reference/idispeventimpl-class.md) членов перед [вызовом DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) или [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)<br/>
[Композитные макросы управления](../../atl/reference/composite-control-macros.md)
