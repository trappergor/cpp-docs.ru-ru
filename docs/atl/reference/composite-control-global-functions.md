---
title: Глобальные функции составного элемента управления
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
ms.openlocfilehash: d86978c6bf8aba87828cdda91c3e849a2f755a90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525272"
---
# <a name="composite-control-global-functions"></a>Глобальные функции составного элемента управления

Эти функции обеспечивают поддержку для создания диалоговых окон, а также для создания, размещения и лицензирование элементов управления ActiveX.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|Создает модальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. Открывшемся диалоговом окне может содержать элементы управления ActiveX.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|Создает немодальное диалоговое окно на основе шаблона диалогового окна, предоставленного пользователем. Открывшемся диалоговом окне может содержать элементы управления ActiveX.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Создает элемент управления ActiveX, инициализирует его, на котором она размещена в указанном окне и возвращает указатель интерфейса (или указателей) из элемента управления.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, на котором она размещена в указанном окне и возвращает указатель интерфейса (или указателей) из элемента управления.|
|[AtlAxAttachControl](#atlaxattachcontrol)|Присоединяет ранее созданный элемент управления к указанному окну.|
|[AtlAxGetHost](#atlaxgethost)|Позволяет получить прямой указатель интерфейса на контейнер для указанного окна (если таковые имеются), по его указателю.|
|[AtlAxGetControl](#atlaxgetcontrol)|Позволяет получить прямой указатель интерфейса для элемента управления, содержащегося в заданном окне (если таковые имеются), по его указателю.|
|[AtlSetChildSite](#atlsetchildsite)|Инициализирует `IUnknown` дочернего сайта.|
|[AtlAxWinInit](#atlaxwininit)|Инициализирует код размещения для AxWin объектов.|
|[AtlAxWinTerm](#atlaxwinterm)|Отменяет инициализацию код размещения для AxWin объектов.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Возвращает сведения об интерфейсе источника по умолчанию объекта.|

## <a name="requirements"></a>Требования

**Заголовок:** atlhost.h

##  <a name="atlaxdialogbox"></a>  AtlAxDialogBox

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
[in] Идентифицирует экземпляр модуля, исполняемый файл содержит шаблон диалогового окна.

*lpTemplateName*<br/>
[in] Определяет шаблон диалогового окна. Этот параметр является указатель на строку нуль-символом, который указывает имя шаблона диалогового окна или целочисленное значение, указывающее идентификатор ресурса шаблона диалогового окна. Если параметр задает идентификатор ресурса, его старшее слово должно быть равно нулю, и его младшее слово должно содержать идентификатор. Можно использовать [MAKEINTRESOURCE](/windows/desktop/api/winuser/nf-winuser-makeintresourcea) макрос для создания этого значения.

*hWndParent*<br/>
[in] Определяет окно, которому принадлежит диалоговое окно.

*lpDialogProc*<br/>
[in] Указывает процедуру диалогового окна. Дополнительные сведения о процедуру диалогового окна см. в разделе [DialogProc](https://msdn.microsoft.com/library/windows/desktop/ms645469).

*dwInitParam*<br/>
[in] Указывает значение для передачи в диалоговом окне *lParam* параметр WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Для использования `AtlAxDialogBox` с помощью шаблона диалогового окна, содержащий элемент управления ActiveX, укажите допустимую строку CLSID, APPID или URL-адрес как *текст* поле **УПРАВЛЕНИЯ** раздел ресурса диалогового окна, вместе с " AtlAxWin80» как *имя класса* поле в том же разделе. Следующий подход демонстрирует какие является допустимым **УПРАВЛЕНИЯ** раздел может выглядеть так:

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

Дополнительные сведения о редактировании ресурсов см. в разделе [как: открытие файла описания ресурсов в текстовом формате](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Дополнительные сведения об инструкциях определения ресурсов элемента управления, см. в разделе [общих параметров управления](/windows/desktop/menurc/common-control-parameters) в разделе Windows SDK *: SDK Tools*.

Дополнительные сведения в диалоговых окнах в целом см. [DialogBox](/windows/desktop/api/winuser/nf-winuser-dialogboxa) и [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) в пакете Windows SDK.

##  <a name="atlaxcreatedialog"></a>  AtlAxCreateDialog

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
[in] Идентифицирует экземпляр модуля, исполняемый файл содержит шаблон диалогового окна.

*lpTemplateName*<br/>
[in] Определяет шаблон диалогового окна. Этот параметр является указатель на строку нуль-символом, который указывает имя шаблона диалогового окна или целочисленное значение, указывающее идентификатор ресурса шаблона диалогового окна. Если параметр задает идентификатор ресурса, его старшее слово должно быть равно нулю, и его младшее слово должно содержать идентификатор. Можно использовать [MAKEINTRESOURCE](/windows/desktop/api/winuser/nf-winuser-makeintresourcea) макрос для создания этого значения.

*hWndParent*<br/>
[in] Определяет окно, которому принадлежит диалоговое окно.

*lpDialogProc*<br/>
[in] Указывает процедуру диалогового окна. Дополнительные сведения о процедуру диалогового окна см. в разделе [DialogProc](https://msdn.microsoft.com/library/windows/desktop/ms645469).

*dwInitParam*<br/>
[in] Указывает значение для передачи в диалоговом окне *lParam* параметр WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Открывшемся диалоговом окне может содержать элементы управления ActiveX.

См. в разделе [CreateDialog](/windows/desktop/api/winuser/nf-winuser-createdialoga) и [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) в Windows SDK.

##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl

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
Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:

- ProgID, например «MSCAL. Calendar.7»

- CLSID, такие как «{8E27C92B-1264-101C-8A2F-040224009C02}»

- URL-адрес, например "http://www.microsoft.com"

- Ссылку на активный документ, например, «file://\\\Documents\MyDoc.doc»

- Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY >\<парными >»

   > [!NOTE]
   > «MSHTML:» должен предшествовать фрагмент HTML, таким образом, чтобы он обозначается как поток MSHTML.

*hWnd*<br/>
[in] Дескриптор окна, элемент управления будет подключен к.

*pStream*<br/>
[in] Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
[out] Адрес указателя, который будет получать `IUnknown` контейнера. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Это глобальная функция дает тот же результат, что и вызов метода [AtlAxCreateControlEx](#atlaxcreatecontrolex)(*lpszName*, *hWnd*, *pStream*, NULL, NULL, ИМЕЕТ ЗНАЧЕНИЕ NULL, NULL);.

Чтобы создать лицензированный элемент управления ActiveX, см. в разделе [AtlAxCreateControlLic](#atlaxcreatecontrollic).

##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx

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
Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:

- ProgID, например «MSCAL. Calendar.7»

- CLSID, такие как «{8E27C92B-1264-101C-8A2F-040224009C02}»

- URL-адрес, например "http://www.microsoft.com"

- Ссылку на активный документ, например, «file://\\\Documents\MyDoc.doc»

- Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY >\<парными >»

   > [!NOTE]
   > «MSHTML:» должен предшествовать фрагмент HTML, таким образом, чтобы он обозначается как поток MSHTML.

*hWnd*<br/>
[in] Дескриптор окна, элемент управления будет подключен к.

*pStream*<br/>
[in] Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
[out] Адрес указателя, который будет получать `IUnknown` контейнера. Может иметь значение NULL.

*ppUnkControl*<br/>
[out] Адрес указателя, который будет получать `IUnknown` созданного элемента управления. Может иметь значение NULL.

*iidSink*<br/>
Идентификатор исходящего интерфейса на содержащийся объект.

*punkSink*<br/>
Указатель на `IUnknown` интерфейс приемника объекта должен быть подключен к точки подключения, заданные *iidSink* на содержащийся объект после успешного создания содержащийся объект.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

`AtlAxCreateControlEx` аналогичен [AtlAxCreateControl](#atlaxcreatecontrol) , но также позволяет получать указатель интерфейса на вновь созданный элемент управления и настройка приемник событий для получения события, инициируемые элементом управления.

Чтобы создать лицензированный элемент управления ActiveX, см. в разделе [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).

##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic

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
Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:

- ProgID, например «MSCAL. Calendar.7»

- CLSID, такие как «{8E27C92B-1264-101C-8A2F-040224009C02}»

- URL-адрес, например "http://www.microsoft.com"

- Ссылку на активный документ, например, «file://\\\Documents\MyDoc.doc»

- Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY >\<парными >»

   > [!NOTE]
   > «MSHTML:» должен предшествовать фрагмент HTML, таким образом, чтобы он обозначается как поток MSHTML.

*hWnd*<br/>
Дескриптор окна, элемент управления будет подключен к.

*pStream*<br/>
Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
Адрес указателя, который будет получать `IUnknown` контейнера. Может иметь значение NULL.

*bstrLic*<br/>
BSTR, содержащий лицензии для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример демонстрирует использование `AtlAxCreateControlLic`.

##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx

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
Указатель на строку для передачи элементу управления. Должен быть отформатирован в одном из следующих способов:

- ProgID, например «MSCAL. Calendar.7»

- CLSID, такие как «{8E27C92B-1264-101C-8A2F-040224009C02}»

- URL-адрес, например "http://www.microsoft.com"

- Ссылку на активный документ, например, «file://\\\Documents\MyDoc.doc»

- Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY >\<парными >»

   > [!NOTE]
   > «MSHTML:» должен предшествовать фрагмент HTML, таким образом, чтобы он обозначается как поток MSHTML.

*hWnd*<br/>
Дескриптор окна, элемент управления будет подключен к.

*pStream*<br/>
Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
Адрес указателя, который будет получать `IUnknown` контейнера. Может иметь значение NULL.

*ppUnkControl*<br/>
[out] Адрес указателя, который будет получать `IUnknown` созданного элемента управления. Может иметь значение NULL.

*iidSink*<br/>
Идентификатор исходящего интерфейса на содержащийся объект.

*punkSink*<br/>
Указатель на `IUnknown` интерфейс приемника объекта должен быть подключен к точки подключения, заданные *iidSink* на содержащийся объект после успешного создания содержащийся объект.

*bstrLic*<br/>
BSTR, содержащий лицензии для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

`AtlAxCreateControlLicEx` аналогичен [AtlAxCreateControlLic](#atlaxcreatecontrollic) , но также позволяет получать указатель интерфейса на вновь созданный элемент управления и настройка приемник событий для получения события, инициируемые элементом управления.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример демонстрирует использование `AtlAxCreateControlLicEx`.

##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl

Присоединяет ранее созданный элемент управления к указанному окну.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
[in] Указатель на `IUnknown` элемента управления.

*hWnd*<br/>
[in] Дескриптор окна, где будет размещаться элемент управления.

*ppUnkContainer*<br/>
[out] Указатель на указатель на `IUnknown` объекта-контейнера.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Используйте [AtlAxCreateControlEx](#atlaxcreatecontrolex) и [AtlAxCreateControl](#atlaxcreatecontrol) чтобы одновременно создать и подключить элемент управления.

> [!NOTE]
>  Присоединяемый объект элемента управления необходимо правильно инициализировать перед вызовом `AtlAxAttachControl`.

##  <a name="atlaxgethost"></a>  AtlAxGetHost

Получает прямой указатель интерфейса на контейнер для указанного окна (если имеется) по его указателю.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Параметры

*h*<br/>
[in] Дескриптор окна, на котором размещается элемент управления.

*PP*<br/>
[out] `IUnknown` Контейнера элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl

Получает прямой указатель интерфейса на элемент управления, который содержится в заданном окне (на основе его указателя).

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Параметры

*h*<br/>
[in] Дескриптор окна, на котором размещается элемент управления.

*PP*<br/>
[out] `IUnknown` , Размещенного элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

##  <a name="atlsetchildsite"></a>  AtlSetChildSite

Вызывайте эту функцию, чтобы задать для сайта дочернего объекта к `IUnknown` родительского объекта.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>Параметры

*punkChild*<br/>
[in] Указатель на `IUnknown` интерфейс дочернего элемента.

*punkParent*<br/>
[in] Указатель на `IUnknown` интерфейс родительского элемента.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="atlaxwininit"></a>  AtlAxWinInit

Эта функция инициализирует размещения кода путем регистрации элемента управления ATL **«AtlAxWin80»** и **«AtlAxWinLic80»** классы окна, а также пару пользовательских сообщений окна.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнена инициализация код размещения элемента управления; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Эту функцию необходимо вызывать перед использованием элемента управления ATL, интерфейс API размещения. После вызова этой функции **«AtlAxWin»** класс окна может использоваться в вызовах [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) или [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa), как описано в пакете Windows SDK.

##  <a name="atlaxwinterm"></a>  AtlAxWinTerm

Эта функция отменяет инициализацию элемента управления ATL кода размещения **«AtlAxWin80»** и **«AtlAxWinLic80»** классов окон.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Эта функция просто вызывает [UnregisterClass](https://msdn.microsoft.com/library/windows/desktop/ms644899) как описано в пакете Windows SDK.

Вызывайте эту функцию для очистки после всех существующих окон узла уничтожены, если вызван [AtlAxWinInit](#atlaxwininit) и больше не требуется создавать узла windows. Если вы не вызываете эту функцию, класс окна будет отменена автоматически при прекращении процесса.

##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface

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

*punkObj*<br/>
[in] Указатель на объект, для которого должны быть возвращены сведения.

*plibid*<br/>
[out] Указатель на идентификатор LIBID библиотеки типов, содержащий определение исходного интерфейса.

*piid*<br/>
[out] Указатель на идентификатор интерфейса объекта по умолчанию исходного интерфейса.

*pdwMajor*<br/>
[out] Указатель на основной номер версии библиотеки типов, содержащий определение исходного интерфейса.

*pdwMinor*<br/>
[out] Указатель на дополнительный номер версии библиотеки типов, содержащий определение исходного интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`AtlGetObjectSourceInterface` можно предоставить вам идентификатор интерфейса исходный интерфейс по умолчанию, а также идентификатор LIBID и основные и дополнительные номера версий библиотеки типов, описывающие этот интерфейс.

> [!NOTE]
>  Для этой функции для успешного получения запрошенные сведения, объект, представленный *punkObj* должен реализовывать `IDispatch` (и возвращают сведения о типе через `IDispatch::GetTypeInfo`), а также он должен также реализовывать либо `IProvideClassInfo2` или `IPersist`. Сведения о типе для интерфейса источника должен быть в той же библиотеки типов, как сведения о типе `IDispatch`.

### <a name="example"></a>Пример

В приведенном ниже примере показано, как можно определить класс приемника событий, `CEasySink`, которая сокращает число аргументов шаблона, которые можно передать `IDispEventImpl` на основе компьютера essentials. `EasyAdvise` и `EasyUnadvise` использовать `AtlGetObjectSourceInterface` для инициализации [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) члены перед вызовом [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) или [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макросы для работы с составными элементами управления](../../atl/reference/composite-control-macros.md)
