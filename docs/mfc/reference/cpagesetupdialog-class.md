---
title: Класс CPageSetupDialog
ms.date: 11/04/2016
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
ms.openlocfilehash: 218ed24ccf56854622e20936299fcc2e8a3d0fa9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374790"
---
# <a name="cpagesetupdialog-class"></a>Класс CPageSetupDialog

Инкапсулирует службы, предоставляемые стандартным диалоговым окном OLE "Параметры страницы" Windows с дополнительной поддержкой установки и изменения полей печати.

## <a name="syntax"></a>Синтаксис

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPageSetupДиалог::CPageSetupDialog](#cpagesetupdialog)|Формирует объект `CPageSetupDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPageSetupДиалог::CreatePrinterDC](#createprinterdc)|Создает контекст устройства для печати.|
|[CPageSetupДиалог::DoModal](#domodal)|Отображает диалоговую коробку и позволяет пользователю сделать выбор.|
|[CPageSetupДиалог::GetDeviceName](#getdevicename)|Возвращает имя устройства принтера.|
|[CPageSetupДиалог::GetDevMode](#getdevmode)|Возвращает текущий DEVMODE принтера.|
|[CPageSetupДиалог::GetDriverName](#getdrivername)|Возвращает драйвер, используемый принтером.|
|[CPageSetupДиалог::GetMargins](#getmargins)|Возвращает текущие параметры поля принтера.|
|[CPageSetupДиалог::GetPaperSize](#getpapersize)|Возвращает размер бумаги принтера.|
|[CPageSetupДиалог::GetPortName](#getportname)|Возвращает имя порта вывода.|
|[CPageSetupДиалог::OnDrawPage](#ondrawpage)|Вызывается фреймворком для визуализации изображения экрана печатной страницы.|
|[CPageSetupДиалог::PreDrawPage](#predrawpage)|Вызывается в рамках перед визуализацией изображения экрана печатной страницы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPageSetupДиалог::m_psd](#m_psd)|Структура, используемая для `CPageSetupDialog` настройки объекта.|

## <a name="remarks"></a>Remarks

Этот класс предназначен для того, чтобы занять место диалогового окна Print Setup.

Чтобы использовать `CPageSetupDialog` объект, сначала создайте `CPageSetupDialog` объект с помощью конструктора. После построения диалогового окна можно установить или изменить `m_psd` любые значения в элементе данных, чтобы инициализировать значения элементов управления диалогового окна. Структура [m_psd](#m_psd) типа PAGESETUPDLG.

После инициализации элементов `DoModal` управления диалоговым полем позвоните функции участника для отображения диалогового окна и позвольте пользователю выбрать параметры печати. `DoModal`возвращает сярот, выбрал ли пользователь кнопку OK (IDOK) или «Отменить» (IDCANCEL).

При `DoModal` возврате IDOK можно `CPageSetupDialog`использовать несколько функций `m_psd` членов или получить доступ к пользователю данных для получения информации, вводимых пользователем.

> [!NOTE]
> После того, как общий диалоговый ящик УСТАНОВКи СТРАНИЦЫ OLE будет отклонен, любые изменения, внесенные пользователем, не будут сохранены инфраструктурой. Само приложение может сохранить любые значения из этого диалогового окна в постоянное место, например, член документа приложения или класс приложения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>CPageSetupДиалог::CPageSetupDialog

Вызовите эту `CPageSetupDialog` функцию для построения объекта.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Один или несколько флагов можно использовать для настройки настроек диалогового окна. Значения можно комбинировать с помощью оператора bitwise-OR. Данные величины имеют следующие значения:

- PSD_DEFAULTMINMARGINS устанавливает минимальную допустимую ширину поля страницы, которая будет такой же, как и минимумы принтера. Этот флаг игнорируется, если указаны PSD_MARGINS и PSD_MINMARGINS флаги.

- PSD_INWININIINTLMEASURE не реализован.

- PSD_MINMARGINS Вызывает использование системы значений, `rtMinMargin` указанных в члене, в качестве минимально допустимой ширины для левой, верхней, правой и нижней краев. Система предотвращает ввод пользователя шириной, которая меньше указанного минимума. Если PSD_MINMARGINS не указана, система устанавливает минимально допустимую ширину до допустимых принтером.

- PSD_MARGINS активирует область контроля за запасом.

- PSD_INTHOUSANDTHSOFINCHES Вызывает единицы диалогового окна, которые будут измеряться в 1/1000 дюйма.

- PSD_INHUNDREDTHSOFMILLIMETERS Вызывает единицы диалогового окна, которые измеряются в 1/100 миллиметра.

- PSD_DISABLEMARGINS отсражает элементы управления полем диалогового поля.

- PSD_DISABLEPRINTER отстегивает кнопку принтера.

- PSD_NOWARNING предотвращает отображение предупреждающих сообщений при отсутствии принтера по умолчанию.

- PSD_DISABLEORIENTATION отстраняет управление диалогом ориентации страницы.

- PSD_RETURNDEFAULT `CPageSetupDialog` причины для возврата структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES,](/windows/win32/api/commdlg/ns-commdlg-devnames) которые инициализированы для системного принтера по умолчанию без отображения диалогового окна. Предполагается, что `hDevNames` `hDevMode` оба и являются NULL; в противном случае функция возвращает ошибку. Если принтер системы по умолчанию поддерживается старым драйвером принтера `hDevNames` (ранее, чем версия Windows 3.0), возвращается только; `hDevMode` NULL.

- PSD_DISABLEPAPER отскакивает от контроля выбора бумаги.

- PSD_SHOWHELP Вызывает диалоговую будку для отображания кнопки справки. Участник `hwndOwner` не должен быть NULL, если указан этот флаг.

- PSD_ENABLEPAGESETUPHOOK включает функцию `lpfnSetupHook`крючка, указанную в.

- PSD_ENABLEPAGESETUPTEMPLATE Вызывает операционную систему для создания диалогового окна `hInstance` с `lpSetupTemplateName`помощью шаблона диалогового окна, идентифицированного и .

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE указывает `hInstance` на то, что идентифицирует блок данных, содержащий предварительно загруженный шаблон диалогового окна. Система игнорирует, `lpSetupTemplateName` если этот флаг указан.

- PSD_ENABLEPAGEPAINTHOOK Включает функцию `lpfnPagePaintHook`крючка, указанную в .

- PSD_DISABLEPAGEPAINTING отражает область ничьей в диалоговом поле.

*pParentWnd*<br/>
Указатель на родителей или владельца диалогового окна.

### <a name="remarks"></a>Remarks

Используйте функцию [DoModal](../../mfc/reference/cdialog-class.md#domodal) для отображения диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

## <a name="cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPageSetupДиалог::CreatePrinterDC

Создает контекст устройства принтера из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES.](/windows/win32/api/commdlg/ns-commdlg-devnames)

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Обработка к вновь созданному контексту устройства принтера (DC).

## <a name="cpagesetupdialogdomodal"></a><a name="domodal"></a>CPageSetupДиалог::DoModal

Вызовите эту функцию для отображения общего диалогового окна УСТАНОВКи страницы WINDOWS OLE и позвольте пользователю выбрать различные параметры настройки печати, такие как поля печати, размер и ориентация бумаги и принтера назначения.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK или IDCANCEL. Если IDCANCEL возвращается, позвоните в функцию Windows [CommDlgExtendedError,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) чтобы определить, произошла ли ошибка.

IDOK и IDCANCEL являются константами, указывающими на то, выбрал ли пользователь кнопку OK или Cancel.

### <a name="remarks"></a>Remarks

Кроме того, пользователь может получить доступ к опциям настройки принтера, таким как расположение сети и свойства, характерные для выбранного принтера.

Если вы хотите инициализировать различные параметры диалога `m_psd` настройки страницы, установив `DoModal`членов структуры, вы должны сделать это перед вызовом и после построения объекта диалога. После `DoModal`вызова, вызов других функций участника для получения настроек или ввода информации пользователем в поле диалога.

Если вы хотите распространить текущие настройки, введенные пользователем, позвоните в [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Эта функция берет информацию из `CPageSetupDialog` объекта и инициализирует и выбирает новый принтер DC с соответствующими атрибутами.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Пример

  Смотрите пример [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).

## <a name="cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>CPageSetupДиалог::GetDeviceName

Вызовите `DoModal` эту функцию после получения имени выбранного в настоящее время принтера.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя устройства, используемое объектом. `CPageSetupDialog`

## <a name="cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>CPageSetupДиалог::GetDevMode

Вызов эту функцию после вызова `DoModal` для получения информации о контексте устройства принтера `CPageSetupDialog` объекта.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Структура данных [DEVMODE,](/windows/win32/api/wingdi/ns-wingdi-devmodea) содержащая информацию о инициализации устройства и среде драйвера печати. Вы должны разблокировать память, взятую этой структурой, с помощью функции Windows [GlobalUnlock,](/windows/win32/api/winbase/nf-winbase-globalunlock) описанной в SDK Windows.

## <a name="cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>CPageSetupДиалог::GetDriverName

Вызовите эту функцию после вызова [DoModal,](../../mfc/reference/cprintdialog-class.md#domodal) чтобы получить имя драйвера устройства принтера, определяемого системой.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указание `CString` системного имени драйвера.

### <a name="remarks"></a>Remarks

Используйте указатель `CString` на объект, `GetDriverName` возвращенный `lpszDriverName` в качестве значения в вызове в [CDC:CreateDC.](../../mfc/reference/cdc-class.md#createdc)

## <a name="cpagesetupdialoggetmargins"></a><a name="getmargins"></a>CPageSetupДиалог::GetMargins

Вызов эту функцию `DoModal` после вызова, чтобы получить поля драйвера устройства принтера.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Параметры

*lpRectMargins*<br/>
Указатель на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) который описывает (в 1/1000 дюймов или 1/100 мм) поля печати для выбранного в настоящее время принтера. Пройдите NULL для этого параметра, если вы не заинтересованы в этом прямоугольнике.

*lpRectMinMargins*<br/>
Указатель на `RECT` структуру или `CRect` объект, который описывает (в 1/1000 дюймов или 1/100 мм) минимальные поля печати для выбранного в настоящее время принтера. Пройдите NULL для этого параметра, если вы не заинтересованы в этом прямоугольнике.

## <a name="cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>CPageSetupДиалог::GetPaperSize

Вызовите эту функцию, чтобы получить размер бумаги, выбранной для печати.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize,](../../atl-mfc-shared/reference/csize-class.md) содержащий размер бумаги (в 1/1000 дюймов или 1/100 мм), выбранный для печати.

## <a name="cpagesetupdialoggetportname"></a><a name="getportname"></a>CPageSetupДиалог::GetPortName

Вызов исчерпав эту функцию после вызова, `DoModal` чтобы получить имя выбранного в настоящее время порта принтера.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название выбранного в настоящее время порта принтера.

## <a name="cpagesetupdialogm_psd"></a><a name="m_psd"></a>CPageSetupДиалог::m_psd

Структура типа PAGESETUPDLG, члены которой хранят характеристики объекта диалога.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Remarks

После построения `CPageSetupDialog` объекта можно `m_psd` использовать для установки различных аспектов диалогового окна перед вызовом функции `DoModal` участника.

Если вы `m_psd` измените напрямую данный, вы отмените любое поведение по умолчанию.

Для получения дополнительной информации о структуре [PAGESETUPDLG](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw) см.

Смотрите пример [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).

## <a name="cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>CPageSetupДиалог::OnDrawPage

Вызывается рамки, чтобы нарисовать изображение экрана печатной страницы.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства принтера.

*nСообщение*<br/>
Упоняет сообщение с указанием области нарисованной страницы. Может применяться один из перечисленных ниже типов.

- WM_PSD_FULLPAGERECT всю область страницы.

- WM_PSD_MINMARGINRECT Текущая минимальная маржа.

- WM_PSD_MARGINRECT Текущая маржа.

- WM_PSD_GREEKTEXTRECT Содержание страницы.

- WM_PSD_ENVSTAMPRECT области зарезервированы для почтовой марки представления.

- WM_PSD_YAFULLPAGERECT area для представления обратного адреса. Эта область распространяется на края области страницы образца.

*lpRect*<br/>
Указатель на объект [CRect](../../atl-mfc-shared/reference/crect-class.md) или [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащий координаты области чертежа.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение при обращении; в противном случае 0.

### <a name="remarks"></a>Remarks

Это изображение затем отображается как часть общего диалога OL Page Setup. Реализация по умолчанию рисует изображение страницы текста.

Переопределить эту функцию, чтобы настроить рисунок определенной области изображения или всего изображения. Вы можете сделать это с помощью оператора **коммутатора** с выписками **о случаях,** проверяя значение *nMessage.* Например, для настройки рендеринга содержимого изображения страницы можно использовать следующий пример кода:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

Обратите внимание, что вам не нужно обрабатывать каждый случай *nMessage*. Вы можете выбрать для обработки одного компонента изображения, несколько компонентов изображения, или всей области.

## <a name="cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>CPageSetupДиалог::PreDrawPage

Вызывается рамки перед рисованием изображения экрана печатной страницы.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Параметры

*wPaper*<br/>
Определяет значение, указывававое размер бумаги. Это значение может быть одним из **DMPAPER_** значений, перечисленных в описании структуры [DEVMODE.](/windows/win32/api/wingdi/ns-wingdi-devmodea)

*wFlags*<br/>
Указывает ориентацию бумаги или конверта, а также является ли принтер точечной матрицей или устройством HPPCL (Hewlett Packard Printer Control Language). Этот параметр может принимать одно из следующих значений:

- 0x001 Бумага в ландшафтном режиме (точечная матрица)

- 0x003 Бумага в ландшафтном режиме (HPPCL)

- 0x005 Бумага в портретном режиме (точка матрицы)

- 0x007 Бумага в портретном режиме (HPPCL)

- Конверт 0x00b в ландшафтном режиме (HPPCL)

- 0x00d Конверт в портретном режиме (точка матрицы)

- 0x019 Конверт в ландшафтном режиме (точка матрицы)

- Конверт 0x01f в портретном режиме (точка матрицы)

*pPSD*<br/>
Указатель на структуру `PAGESETUPDLG`. Для получения дополнительной информации о [PAGESETUPDLG,](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw)см.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение при обращении; в противном случае 0.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы настроить рисунок изображения. Если вы переопределить эту функцию и вернуть правду, вы должны нарисовать все изображение. Если вы переопределяете эту функцию и возвращаете FALSE, все изображение по умолчанию нарисовано инфраструктурой.

## <a name="see-also"></a>См. также раздел

[MFC Образец WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[Класс CCommonДиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
