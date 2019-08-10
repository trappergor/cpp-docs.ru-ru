---
title: Класс Кпажесетупдиалог
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
ms.openlocfilehash: a9009c4ea08771949cea2c44e4f6265783ced35a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916938"
---
# <a name="cpagesetupdialog-class"></a>Класс Кпажесетупдиалог

Инкапсулирует службы, предоставляемые стандартным диалоговым окном OLE "Параметры страницы" Windows с дополнительной поддержкой установки и изменения полей печати.

## <a name="syntax"></a>Синтаксис

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Создает объект `CPageSetupDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Создает контекст устройства для печати.|
|[Кпажесетупдиалог::D Омодал](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Возвращает имя устройства принтера.|
|[CPageSetupDialog::GetDevMode](#getdevmode)|Возвращает текущий DEVMODE принтера.|
|[Кпажесетупдиалог:: GetDriverName](#getdrivername)|Возвращает драйвер, используемый принтером.|
|[CPageSetupDialog::GetMargins](#getmargins)|Возвращает текущие настройки полей принтера.|
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Возвращает размер бумаги принтера.|
|[CPageSetupDialog::GetPortName](#getportname)|Возвращает имя выходного порта.|
|[Кпажесетупдиалог:: Ондравпаже](#ondrawpage)|Вызывается платформой для отрисовки экранного изображения печатной страницы.|
|[Кпажесетупдиалог::P Редравпаже](#predrawpage)|Вызывается структурой перед отрисовкой экранного изображения печатной страницы.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|Структура, используемая для настройки `CPageSetupDialog` объекта.|

## <a name="remarks"></a>Примечания

Этот класс предназначен для размещения диалогового окна «Настройка печати».

Чтобы использовать `CPageSetupDialog` объект, сначала создайте объект `CPageSetupDialog` с помощью конструктора. После создания диалогового окна можно задать или изменить любые значения в `m_psd` элементе данных, чтобы инициализировать значения элементов управления диалогового окна. Структура [m_psd](#m_psd) имеет тип пажесетупдлг.

После инициализации элементов управления диалогового окна вызовите `DoModal` функцию члена, чтобы открыть диалоговое окно и позволить пользователю выбрать параметры печати. `DoModal`Возвращает значение, указывающее, выбрал пользователь кнопку ОК (ИДОК) или Отмена (ИДКАНЦЕЛ).

Если `DoModal` возвращает идок, можно использовать `CPageSetupDialog`несколько `m_psd` функций члена или получить доступ к элементу данных, чтобы получить данные, введенные пользователем.

> [!NOTE]
>  После закрытия диалогового окна «Общие параметры OLE-страницы» все изменения, внесенные пользователем, не будут сохранены платформой. Приложение может сохранить любые значения из этого диалогового окна в постоянное расположение, например член приложения или класса приложения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксдлгс. h

##  <a name="cpagesetupdialog"></a>  CPageSetupDialog::CPageSetupDialog

Вызовите эту функцию для создания `CPageSetupDialog` объекта.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна. Значения можно комбинировать с помощью оператора побитового или. Эти значения имеют следующее значение:

- PSD_DEFAULTMINMARGINS устанавливает минимально допустимую ширину полей страницы в соответствии с минимальными размерами принтера. Этот флаг пропускается, если также указаны флаги PSD_MARGINS и PSD_MINMARGINS.

- PSD_INWININIINTLMEASURE не реализован.

- PSD_MINMARGINS заставляет систему использовать значения, указанные в `rtMinMargin` элементе, как минимально допустимую ширину для левого, верхнего, правого и нижнего полей. Система не дает пользователю вводить ширину, которая меньше указанного минимума. Если PSD_MINMARGINS не указан, система устанавливает минимально допустимую ширину для разрешенных принтером.

- PSD_MARGINS активирует область элементов управления полями.

- PSD_INTHOUSANDTHSOFINCHES приводит к тому, что единицы измерения диалогового окна измеряются в 1/1000 дюйма.

- PSD_INHUNDREDTHSOFMILLIMETERS приводит к тому, что единицы измерения диалогового окна измеряются в 1/100 миллиметра.

- PSD_DISABLEMARGINS отключает элементы управления «поле».

- PSD_DISABLEPRINTER отключает кнопку "принтер".

- PSD_NOWARNING предотвращает отображение предупреждающего сообщения при отсутствии принтера по умолчанию.

- PSD_DISABLEORIENTATION отключает элемент управления диалогового окна «ориентация страницы».

- PSD_RETURNDEFAULT приводит `CPageSetupDialog` к возврату структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) , инициализированных для принтера системы по умолчанию без отображения диалогового окна. Предполагается, что оба `hDevNames` аргумента и `hDevMode` имеют значение null. в противном случае функция возвращает ошибку. Если системный принтер по умолчанию поддерживается старым драйвером принтера (более ранним, чем Windows версии 3,0) `hDevNames` , возвращается только. `hDevMode` имеет значение null.

- PSD_DISABLEPAPER отключает элемент управления "Выбор бумаги".

- PSD_SHOWHELP заставляет диалоговое окно отобразить кнопку "Справка". Если указан этот флаг, членнедолжениметьзначениеnull.`hwndOwner`

- PSD_ENABLEPAGESETUPHOOK включает функцию-обработчик, указанную в `lpfnSetupHook`.

- PSD_ENABLEPAGESETUPTEMPLATE заставляет операционную систему создать диалоговое окно, используя диалоговое окно шаблон диалогового окна `hInstance` , `lpSetupTemplateName`определяемое и.

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE указывает, `hInstance` что определяет блок данных, содержащий предварительно загруженный шаблон диалогового окна. Система не учитывает `lpSetupTemplateName` , если указан этот флаг.

- PSD_ENABLEPAGEPAINTHOOK включает функцию-обработчик, указанную в `lpfnPagePaintHook`.

- PSD_DISABLEPAGEPAINTING отключает область рисования диалогового окна.

*ппарентвнд*<br/>
Указатель на родительский элемент или владелец диалогового окна.

### <a name="remarks"></a>Примечания

Используйте функцию [DoModal](../../mfc/reference/cdialog-class.md#domodal) для вывода диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>Кпажесетупдиалог:: Креатепринтердк

Создает контекст печатающего устройства из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) .

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Обработайте только что созданный контекст устройства печати (DC).

##  <a name="domodal"></a>Кпажесетупдиалог::D Омодал

Эта функция вызывается для отображения диалогового окна Общие параметры OLE страницы Windows и позволяет пользователю выбирать различные параметры печати, такие как поля печати, размер и ориентация бумаги, а также конечный принтер.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

ИДОК или ИДКАНЦЕЛ. Если возвращается ИДКАНЦЕЛ, вызовите функцию Windows [коммдлжекстендедеррор](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) , чтобы определить, произошла ли ошибка.

ИДОК и ИДКАНЦЕЛ — это константы, которые указывают, выбрал ли пользователь кнопку ОК или Отмена.

### <a name="remarks"></a>Примечания

Кроме того, пользователь может получить доступ к параметрам установки принтера, таким как сетевое расположение и свойства, относящиеся к выбранному принтеру.

Если требуется инициализировать различные параметры диалогового окна настройки страницы путем установки элементов `m_psd` структуры, следует сделать это перед вызовом `DoModal`и после создания объекта диалогового окна. После вызова `DoModal`вызовите другие функции члена для получения параметров или данных, вводимых пользователем, в диалоговое окно.

Если вы хотите распространить текущие параметры, введенные пользователем, выполните вызов метода [CWinApp:: селектпринтер](../../mfc/reference/cwinapp-class.md#selectprinter). Эта функция принимает сведения из `CPageSetupDialog` объекта и инициализирует и выбирает новый контроллер домена с правильными атрибутами.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Пример

  См. пример для [кпажесетупдиалог:: кпажесетупдиалог](#cpagesetupdialog).

##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName

Вызовите эту функцию `DoModal` после, чтобы получить имя текущего выбранного принтера.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя устройства, используемое `CPageSetupDialog` объектом.

##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode

Вызовите эту функцию после `DoModal` вызова, чтобы получить сведения о контексте `CPageSetupDialog` устройства печати объекта.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Структура данных [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) , которая содержит сведения об инициализации устройства и среде драйвера печати. Необходимо разблокировать память, занятую этой структурой, с помощью функции Windows [глобалунлокк](/windows/desktop/api/winbase/nf-winbase-globalunlock) , которая описана в Windows SDK.

##  <a name="getdrivername"></a>Кпажесетупдиалог:: GetDriverName

Вызовите эту функцию после вызова [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) , чтобы получить имя драйвера принтера, определенного системой.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение `CString` типа, указывающее имя драйвера, определяемое системой.

### <a name="remarks"></a>Примечания

Используйте указатель на `CString` объект, `GetDriverName` возвращаемый в качестве значения `lpszDriverName` в вызове [CDC:: креатедк](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins

Вызовите эту функцию после вызова метода `DoModal` , чтобы получить поля драйвера печатающего устройства.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Параметры

*лпректмаргинс*<br/>
Указатель на структуру [Rect](/windows/desktop/api/windef/ns-windef-tagrect) или объект [крект](../../atl-mfc-shared/reference/crect-class.md) , описывающий поля печати для текущего выбранного принтера (в 1/1000 дюймах или 1/100 мм). Если вы не заинтересованы в этом прямоугольнике, передайте значение NULL для этого параметра.

*лпректминмаргинс*<br/>
Указатель на `RECT` структуру или `CRect` объект, описывающие минимальное поле печати для выбранного принтера (в 1/1000 дюймах или 1/100 мм). Если вы не заинтересованы в этом прямоугольнике, передайте значение NULL для этого параметра.

##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize

Вызовите эту функцию, чтобы получить размер бумаги, выбранной для печати.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) , содержащий размер бумаги (в 1/1000 дюймах или 1/100 мм), выбранный для печати.

##  <a name="getportname"></a>  CPageSetupDialog::GetPortName

Вызовите эту функцию после `DoModal` вызова, чтобы получить имя текущего выбранного порта принтера.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного в данный момент порта принтера.

##  <a name="m_psd"></a>  CPageSetupDialog::m_psd

Структура типа ПАЖЕСЕТУПДЛГ, члены которой хранят характеристики объекта диалогового окна.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Примечания

После создания `CPageSetupDialog` объекта можно использовать `m_psd` для установки различных аспектов `DoModal` диалогового окна перед вызовом функции-члена.

При непосредственном изменении `m_psd` элемента данных будет переопределено поведение по умолчанию.

Дополнительные сведения о структуре [пажесетупдлг](/windows/desktop/api/commdlg/ns-commdlg-tagpsda) см. в Windows SDK.

См. пример для [кпажесетупдиалог:: кпажесетупдиалог](#cpagesetupdialog).

##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage

Вызывается платформой для отрисовки экранного изображения печатной страницы.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства принтера.

*nсообщение*<br/>
Задает сообщение, указывающее область страницы, на которой выполняется прорисовка. Ниже указаны доступные значения.

- WM_PSD_FULLPAGERECT всю область страницы.

- WM_PSD_MINMARGINRECT текущие минимальные поля.

- WM_PSD_MARGINRECT текущие поля.

- WM_PSD_GREEKTEXTRECT содержимое страницы.

- Область WM_PSD_ENVSTAMPRECT, зарезервированная для представления штампа почтовых марок.

- WM_PSD_YAFULLPAGERECT область для представления адреса возврата. Эта область распространяется на границы области образца страницы.

*лпрект*<br/>
Указатель на объект [крект](../../atl-mfc-shared/reference/crect-class.md) или [Rect](/windows/desktop/api/windef/ns-windef-tagrect) , содержащий координаты области рисования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение при обработке; в противном случае — 0.

### <a name="remarks"></a>Примечания

Это изображение затем отображается как часть диалогового окна «Общие параметры страницы OLE». Реализация по умолчанию рисует изображение страницы текста.

Переопределите эту функцию, чтобы настроить Рисование определенной области изображения или всего изображения. Это можно сделать с помощью оператора **switch** с инструкциями **case** , чтобы проверить значение *nсообщение*. Например, чтобы настроить отрисовку содержимого изображения страницы, можно использовать следующий пример кода:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

Обратите внимание, что не требуется выполнять обработку каждого случая *nсообщение*. Можно выбрать обработку одного компонента изображения, нескольких компонентов изображения или всей области.

##  <a name="predrawpage"></a>Кпажесетупдиалог::P Редравпаже

Вызывается структурой перед отрисовкой экранного изображения печатной страницы.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Параметры

*впапер*<br/>
Задает значение, указывающее размер бумаги. Это значение может быть одним из значений **DMPAPER_** , перечисленных в описании структуры [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) .

*вфлагс*<br/>
Указывает ориентацию бумаги или конверта, а также наличие устройства с точечной матрицей или ориентации для HPPCLHPPCL (язык управления принтерами Hewlett Packard). Этот параметр может принимать одно из следующих значений:

- 0x001 бумага в альбомном режиме (матричный)

- 0x003 бумага в альбомном режиме (ориентации для HPPCLHPPCL)

- 0x005 бумага в книжной ориентации (точечная матрица)

- 0x007 бумага в книжном режиме (ориентации для HPPCLHPPCL)

- Конверт 0x00b в альбомном режиме (ориентации для HPPCLHPPCL)

- Конверт в 0x00 в книжном режиме (матрица точек)

- Конверт 0x019 в альбомной ориентации (матрица точек)

- Конверт 0x01f в книжной ориентации (матрица точек)

*ппсд*<br/>
Указатель на структуру `PAGESETUPDLG`. Дополнительные сведения о [пажесетупдлг](/windows/desktop/api/commdlg/ns-commdlg-tagpsda)см. в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение при обработке; в противном случае — 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы настроить Рисование изображения. Если вы переопределяете эту функцию и возвращаете значение TRUE, необходимо рисовать изображение целиком. Если переопределить эту функцию и вернуть значение FALSE, платформа будет рисовать все изображение по умолчанию.

## <a name="see-also"></a>См. также

[Образец WORDPAD для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
