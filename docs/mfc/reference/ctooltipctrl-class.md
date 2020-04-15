---
title: CToolTipCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
ms.openlocfilehash: fdf91549fd1b911de3af82bb940b92fe5e220b92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365102"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class

Инкапсулирует функциональность элемента управления "всплывающая подсказка" — небольшого всплывающего окна, в котором отображается одна строка текста, описывающая назначение инструмента в приложении.

## <a name="syntax"></a>Синтаксис

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Формирует объект `CToolTipCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CToolTipCtrl:Активировать](#activate)|Активирует и отключает управление наконечником инструмента.|
|[CToolCtrl::AddTool](#addtool)|Регистрирует инструмент с помощью управления наконечником инструмента.|
|[CToolCtrl:AdjustRect](#adjustrect)|Преобразуется между прямоугольником отображения текстовых дисплеев наконечника инструмента и его оконным прямоугольником.|
|[CToolTipCtrl::Создание](#create)|Создает управление наконечником инструмента и `CToolTipCtrl` прикрепляет его к объекту.|
|[CToolTipCtrl::CreateEx](#createex)|Создает управление наконечником инструмента с указанными расширенными `CToolTipCtrl` стилями Windows и прикрепляет его к объекту.|
|[CToolCtrl::DelTool](#deltool)|Удаляет инструмент из управления наконечником инструмента.|
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Извлекает размер наконечника инструмента.|
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Извлекает информацию, такую как размер, положение и текст, окна инструментария, которое отображает текущий элемент управления набором инструментов.|
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Извлекает начальные, всплывающие и переодевнные длительности, которые в настоящее время установлены для управления наконечником инструмента.|
|[CToolTipCtrl:GetMargin](#getmargin)|Извлекает верхние, левые, нижние и правые поля, установленные для окна наконечника инструмента.|
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Извлекает максимальную ширину для окна наконечника инструмента.|
|[CToolCtrl::GetText](#gettext)|Извлекает текст, который элемент управления наконечником инструмента поддерживается для инструмента.|
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Извлекает цвет фона в окне наконечника инструмента.|
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Извлекает цвет текста в окне наконечника инструмента.|
|[CToolTipCtrl::GetTitle](#gettitle)|Получает название текущего элемента управления набором инструментов.|
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Извлекает количество инструментов, поддерживаемых управлением наконечником инструмента.|
|[CToolCtrl::GetToolInfo](#gettoolinfo)|Извлекает информацию, которую контролирует наконечник инструмента об инструменте.|
|[CToolTipCtrl::HitTest](#hittest)|Тестирует точку, чтобы определить, находится ли она в граничащий прямоугольник данного инструмента. Если да, то получает информацию об этом инструменте.|
|[CToolTipCtrl::Pop](#pop)|Удаляет из виду отображено окно наконечника инструмента.|
|[CToolTipCtrl::Popup](#popup)|Вызывает отображение текущего элемента управления ToolTip в координатах последнего сообщения мыши.|
|[CToolTipCtrl::RelayEvent](#relayevent)|Передает сообщение мыши на элемент управления наконечником инструмента для обработки.|
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Устанавливает начальные, всплывающие и переодевнные длительности для управления наконечником инструмента.|
|[CToolTipCtrl::SetMargin](#setmargin)|Устанавливает верхний, левый, нижний и правый края для окна наконечника инструмента.|
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Устанавливает максимальную ширину окна наконечника инструмента.|
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Устанавливает цвет фона в окне наконечника инструмента.|
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Устанавливает цвет текста в окне наконечника инструмента.|
|[CToolTipCtrl::SetTitle](#settitle)|Добавляет стандартную иконку и строку заголовка к наконечнику инструмента.|
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Устанавливает информацию, которую отзыв инструмента поддерживает для инструмента.|
|[CToolCtrl::SetToolRect](#settoolrect)|Устанавливает новый прямоугольник для инструмента.|
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Устанавливает визуальный стиль окна наконечника инструмента.|
|[CToolTipCtrl::Обновление](#update)|Принуждает текущий инструмент к перерисовке.|
|[CToolCtrl:UpdateTipText](#updatetiptext)|Устанавливает текст наконечника инструмента для инструмента.|

## <a name="remarks"></a>Remarks

"Инструмент" - это либо окно, например детское окно или элемент управления, либо прямоугольная область, определяемая приложением, в клиентской зоне окна. Наконечник инструмента скрыт большую часть времени, появляясь только тогда, когда пользователь кладет курсор на инструмент и оставляет его там примерно на полсекунды. Наконечник инструмента появляется рядом с курсором и исчезает, когда пользователь нажимает кнопку мыши или перемещает курсор с инструмента.

`CToolTipCtrl`обеспечивает функциональность для управления первоначальным временем и продолжительностью наконечника инструмента, шириной поля, окружающей текст наконечника инструмента, шириной самого окна наконечника инструмента, а также фоновым и текстовым цветом наконечника инструмента. Один инструмент отзыв управления может предоставить информацию для более чем одного инструмента.

Класс `CToolTipCtrl` обеспечивает функциональность общего управления наконечником инструмента Windows. Этот элемент управления `CToolTipCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Для получения дополнительной информации о возможности советы инструмент, см [Инструмент Советы в Windows не производные от CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).

Для получения дополнительной `CToolTipCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CToolTipCtrl](../../mfc/using-ctooltipctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="ctooltipctrlactivate"></a><a name="activate"></a>CToolTipCtrl:Активировать

Вызов ими функции, чтобы активировать или отключить управление наконечником инструмента.

```
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
Определяет, должен ли элемент управления наконечником быть активирован или отключен.

### <a name="remarks"></a>Remarks

Если *bActivate* является правдой, управление активируется; если FALSE, он деактивирован.

Когда управление наконечником инструмента активна, информация о наконечнике инструмента появляется, когда курсор находится на инструменте, который зарегистрирован с элементом управления; когда он неактивен, информация о наконечнике инструмента не отображается, даже когда курсор находится на инструменте.

### <a name="example"></a>Пример

  Смотрите пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladdtool"></a><a name="addtool"></a>CToolCtrl::AddTool

Регистрирует инструмент с помощью управления наконечником инструмента.

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее инструмент.

*nIDText*<br/>
Идентификатор ресурса строки, содержащий текст для инструмента.

*lpRectTool*<br/>
Указатель на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) содержащую координаты связующего прямоугольника инструмента. Координаты относительно верхнего левого угла клиентской области окна, идентифицированной *pWnd.*

*nIDTool*<br/>
Идентификатор инструмента.

*lpszText*<br/>
Указатель на текст для инструмента. Если этот параметр содержит значение LPSTR_TEXTCALLBACK, сообщения TTN_NEEDTEXT уведомлений переходят к родительскому окну, на которое указывает *pWnd.*

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Параметры *lpRectTool* и *nIDTool* должны быть действительными, или если *lpRectTool* является NULL, *nIDTool* должен быть 0.

Управление наконечником инструмента может быть связано с более чем одним инструментом. Вызовите эту функцию, чтобы зарегистрировать инструмент с помощью управления наконечником инструмента, чтобы информация, хранящаяся в наконечнике инструмента, отображалась, когда курсор находится на инструменте.

> [!NOTE]
> Вы не можете установить наконечник `AddTool`инструмента на статический элемент управления с помощью.

### <a name="example"></a>Пример

  Смотрите пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladjustrect"></a><a name="adjustrect"></a>CToolCtrl:AdjustRect

Преобразуется между прямоугольником элемента управления текстовым дисплеем и его оконным прямоугольником.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Указатель на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) которая содержит либо прямоугольник окна наконечника инструмента, либо прямоугольник ототречности от текстового дисплея.

*bLarger*<br/>
Если true, *lprc* используется для указания прямоугольника отображения текста и получает соответствующий прямоугольник окна. Если FALSE, *lprc* используется для указания прямоугольника окна, и он получает соответствующий прямоугольник отображения текста.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если прямоугольник успешно отрегулирован; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция члена вычисляет прямоугольник отображения текста элемента управления наконечником из его оконного прямоугольника или прямоугольника окна наконечника инструмента, необходимого для отображения заданного прямоугольника отображения текстового дисплея.

Эта функция члена реализует поведение сообщения Win32 [TTM_ADJUSTRECT,](/windows/win32/Controls/ttm-adjustrect)как описано в SDK Windows.

## <a name="ctooltipctrlcreate"></a><a name="create"></a>CToolTipCtrl::Создание

Создает управление наконечником инструмента и `CToolTipCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Определяет родительское окно управления наконечником инструмента, `CDialog`обычно . Она не должна быть NULL.

*dwStyle*<br/>
Определяет стиль управления наконечником инструмента. Дополнительную информацию можно узнать в разделе **«Замечания».**

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CToolTipCtrl` если объект успешно создан; в противном случае 0.

### <a name="remarks"></a>Remarks

Вы строите `CToolTipCtrl` в два этапа. Сначала позвоните конструктору, `CToolTipCtrl` чтобы построить `Create` объект, а затем позвоните, `CToolTipCtrl` чтобы создать управление наконечником инструмента и прикрепить его к объекту.

Параметр *dwStyle* может быть любой комбинацией [стилей окна.](../../mfc/reference/styles-used-by-mfc.md#window-styles) Кроме того, управление наконечником инструмента имеет два стиля, специфичные для классов: TTS_ALWAYSTIP и TTS_NOPREFIX.

|Стиль|Значение|
|-----------|-------------|
|TTS_ALWAYSTIP|Указать, что наконечник инструмента будет отображаться, когда курсор находится на инструменте, независимо от того, является ли окно владельца элемента управления наконечником инструмента активным или неактивным. Без этого стиля элемент управления наконечником инструмента появляется, когда окно владельца инструмента активен, но не когда оно неактивно.|
|TTS_NOPREFIX|Этот стиль предотвращает отключение персонажа амперсанда (&) от строки. Если управление наконечником инструмента не имеет TTS_NOPREFIX стиля, система автоматически лишает символы амперсанда, позволяя приложению использовать ту же строку, что и элемент меню, так и текст в управлении наконечником инструмента.|

Управление наконечником инструмента имеет WS_POPUP и WS_EX_TOOLWINDOW стили окна, независимо от того, указываете ли вы их при создании элемента управления.

Чтобы создать управление наконечником инструмента с расширенными стилями окон, позвоните [CToolTipCtrl::CreateEx](#createex) вместо `Create`.

### <a name="example"></a>Пример

  Смотрите пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlcreateex"></a><a name="createex"></a>CToolTipCtrl::CreateEx

Создает элемент управления (детское окно) `CToolTipCtrl` и ассоциирует его с объектом.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*dwStyle*<br/>
Определяет стиль управления наконечником инструмента. Для получения дополнительной информации смотрите раздел [«Комментарии» «Создать»](#create) для получения дополнительной информации. **Remarks**

*dwStyleEx*<br/>
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно в противном случае 0.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` `Create` вместо того, чтобы применять расширенные стили Windows, указанные в предисловии расширенного стиля Windows **WS_EX_.**

## <a name="ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a>CToolTipCtrl::CToolTipCtrl

Формирует объект `CToolTipCtrl`.

```
CToolTipCtrl();
```

### <a name="remarks"></a>Remarks

Вы должны `Create` позвонить после построения объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

## <a name="ctooltipctrldeltool"></a><a name="deltool"></a>CToolCtrl::DelTool

Удаляет инструмент, указанный *pWnd* и *nIDTool,* из коллекции инструментов, поддерживаемых управлением наконечником инструмента.

```
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее инструмент.

*nIDTool*<br/>
Идентификатор инструмента.

## <a name="ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a>CToolTipCtrl::GetBubbleSize

Извлекает размер наконечника инструмента.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

*lpToolInfo*<br/>
Указатель на структуру [TOOL tip tool TOOLINFO.](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa)

### <a name="return-value"></a>Возвращаемое значение

Размер наконечника инструмента.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_GETBUBBLESIZE,](/windows/win32/Controls/ttm-getbubblesize)как описано в SDK Windows.

## <a name="ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a>CToolTipCtrl::GetCurrentTool

Извлекает информацию, такую как размер, положение и текст, окна инструментария, отображаемые текущим управлением набором инструментов.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpToolInfo*|(ваут) Указатель на структуру [TOOLINFO,](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) которая получает информацию о текущем окне инструментария.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если информация получена успешно; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода получает информацию о текущем окне инструментария.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

## <a name="ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a>CToolTipCtrl::GetDelayTime

Получает начальные, всплывающие и переодевнные длительности, установленные в настоящее время для управления наконечником инструмента.

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>Параметры

*dwDuration*<br/>
Флаг, который определяет, какое значение продолжительности будет извлечено. Этот параметр может быть одним из следующих значений:

- TTDT_AUTOPOP извлекайте продолжительность времени, когда окно наконечника инструмента остается видимым, если указатель неподвижно в прямоугольнике ограничивающего инструмента.

- TTDT_INITIAL извлекайте продолжительность времени, в течение которого указатель должен оставаться неподвижным в связующего прямоугольнике инструмента до того, как появится окно наконечника инструмента.

- TTDT_RESHOW извлекаем время, необходимое для того, чтобы последующие окна наконечника инструмента появлялись при переходе указателя от одного инструмента к другому.

### <a name="return-value"></a>Возвращаемое значение

Указанное время задержки в миллисекундах

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_GETDELAYTIME,](/windows/win32/Controls/ttm-getdelaytime)как описано в SDK Windows.

## <a name="ctooltipctrlgetmargin"></a><a name="getmargin"></a>CToolTipCtrl:GetMargin

Получает верхний, левый, нижний и правый края, установленные для окна наконечника инструмента.

```
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Адрес `RECT` структуры, которая будет получать информацию о марже. Члены структуры [RECT](/previous-versions/dd162897\(v=vs.85\)) не определяют ограничивающий прямоугольник. Для целей этого сообщения члены структуры интерпретируются следующим образом:

|Участник|Представление|
|------------|--------------------|
|`top`|Расстояние между верхней границей и верхней частью текста наконечника инструмента, в пикселях.|
|`left`|Расстояние между левой границей и левым концом текста наконечника, в пикселях.|
|`bottom`|Расстояние между нижней границей и нижней частью текста наконечника, в пикселях.|
|`right`|Расстояние между правой границей и правым концом текста наконечника, в пикселях.|

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_GETMARGIN,](/windows/win32/Controls/ttm-getmargin)как описано в SDK Windows.

## <a name="ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a>CToolTipCtrl::GetMaxTipWidth

Извлекает максимальную ширину для окна наконечника инструмента.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальная ширина окна наконечника инструмента.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_GETMAXTIPWIDTH,](/windows/win32/Controls/ttm-getmaxtipwidth)как описано в SDK Windows.

## <a name="ctooltipctrlgettext"></a><a name="gettext"></a>CToolCtrl::GetText

Извлекает текст, который элемент управления наконечником инструмента поддерживается для инструмента.

```
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Ссылка `CString` на объект, который получает текст инструмента.

*pWnd*<br/>
Указатель на окно, содержащее инструмент.

*nIDTool*<br/>
Идентификатор инструмента.

### <a name="remarks"></a>Remarks

Параметры *pWnd* и *nIDTool* идентифицируют инструмент. Если этот инструмент был ранее зарегистрирован с помощью `CToolTipCtrl::AddTool`управления наконечником инструмента через предыдущий вызов, объект, на который ссылается параметр *str,* назначается тексту инструмента.

## <a name="ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a>CToolTipCtrl::GetTipBkColor

Извлекает цвет фона в окне наконечника инструмента.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) представляющее цвет фона.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_GETTIPBKCOLOR,](/windows/win32/Controls/ttm-gettipbkcolor)как описано в SDK Windows.

## <a name="ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a>CToolTipCtrl::GetTipTextColor

Извлекает цвет текста в окне наконечника инструмента.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) представляющее цвет текста.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_GETTIPTEXTCOLOR,](/windows/win32/Controls/ttm-gettiptextcolor)как описано в SDK Windows.

## <a name="ctooltipctrlgettitle"></a><a name="gettitle"></a>CToolTipCtrl::GetTitle

Получает название текущего элемента управления набором инструментов.

```
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pttgt*|(ваут) Указатель на структуру [TTGETTITLE,](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) содержащую информацию о элементе управления ToolTip. Когда этот метод возвращается, *pszTitle* член структуры [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) указывает на текст заголовка.|

### <a name="remarks"></a>Remarks

Этот метод отправляет [сообщение TTM_GETTITLE,](/windows/win32/Controls/ttm-gettitle) которое описано в SDK Windows.

## <a name="ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a>CToolTipCtrl::GetToolCount

Извлекает количество инструментов, зарегистрированных с помощью управления наконечником инструмента.

```
int GetToolCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Подсчет инструментов, зарегистрированных с помощью управления наконечником инструмента.

## <a name="ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a>CToolCtrl::GetToolInfo

Извлекает информацию, которую контролирует наконечник инструмента об инструменте.

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Параметры

*ToolInfo*<br/>
Ссылка `TOOLINFO` на объект, который получает текст инструмента.

*pWnd*<br/>
Указатель на окно, содержащее инструмент.

*nIDTool*<br/>
Идентификатор инструмента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Члены `hwnd` структуры [TOOLINFO,](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) на которую ссылается *CToolInfo,* идентифицируют инструмент. `uId` Если этот инструмент был зарегистрирован с помощью управления `AddTool`наконечником инструмента через предыдущий вызов, `TOOLINFO` структура заполнена информацией об этом инструменте.

## <a name="ctooltipctrlhittest"></a><a name="hittest"></a>CToolTipCtrl::HitTest

Тестирует точку, чтобы определить, находится ли он в граничащий прямоугольник данного инструмента, и, если да, то получает информацию об этом инструменте.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее инструмент.

*пт*<br/>
Указатель на `CPoint` объект, содержащий координаты точки, которые должны быть проверены.

*lpToolInfo*<br/>
Указатель на структуру [TOOLINFO,](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) содержащую информацию об инструменте.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если точка, указанная информацией о наехте,теста, находится в связующего прямоугольнике инструмента; в противном случае 0.

### <a name="remarks"></a>Remarks

Если эта функция возвращает ненулевое значение, структура, на которую указывает *lpToolInfo,* заполняется информацией о инструменте, внутри которого находится прямоугольник точки.

Структура `TTHITTESTINFO` определяется следующим образом:

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   Определяет ручку инструмента.

- `pt`

   Определяет координаты точки, если точка находится в связующего прямоугольнике инструмента.

- `ti`

   Информация об инструменте. Для получения дополнительной `TOOLINFO` информации о структуре, см. [CToolTipCtrl::GetToolInfo](#gettoolinfo).

## <a name="ctooltipctrlpop"></a><a name="pop"></a>CToolTipCtrl::Pop

Удаляет из представления отображено окно наконечника инструмента.

```
void Pop();
```

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_POP,](/windows/win32/Controls/ttm-pop)как описано в SDK Windows.

## <a name="ctooltipctrlpopup"></a><a name="popup"></a>CToolTipCtrl::Popup

Вызывает отображение текущего элемента управления набором инструментов в координатах последнего сообщения мыши.

```
void Popup();
```

### <a name="remarks"></a>Remarks

Этот метод отправляет [сообщение TTM_POPUP,](/windows/win32/Controls/ttm-popup) которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода отображает окно tooltip.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

## <a name="ctooltipctrlrelayevent"></a><a name="relayevent"></a>CToolTipCtrl::RelayEvent

Передает сообщение мыши на элемент управления наконечником инструмента для обработки.

```
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*lpMsg*<br/>
Указатель на структуру [MSG,](/windows/win32/api/winuser/ns-winuser-msg) содержащую сообщение для ретрансляции.

### <a name="remarks"></a>Remarks

Контроль наконечника инструмента обрабатывает только следующие сообщения, `RelayEvent`которые отправляются ему:

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>Пример

  Смотрите пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a>CToolTipCtrl::SetDelayTime

Устанавливает время задержки для управления наконечником инструмента.

```
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>Параметры

*nDelay*<br/>
Определяет новое время задержки в миллисекундах.

*dwDuration*<br/>
Флаг, который определяет, какое значение продолжительности будет извлечено. Смотрите [CToolTipCtrl::GetDelayTime](#getdelaytime) для описания действительных значений.

*iTime*<br/>
Указанное время задержки, в миллисекундах.

### <a name="remarks"></a>Remarks

Время задержки — это время, в течение которого курсор должен оставаться на инструменте до того, как появится окно наконечника инструмента. Время задержки по умолчанию составляет 500 миллисекунд.

## <a name="ctooltipctrlsetmargin"></a><a name="setmargin"></a>CToolTipCtrl::SetMargin

Устанавливает верхний, левый, нижний и правый края для окна наконечника инструмента.

```
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Адрес `RECT` структуры, содержащей информацию о марже, которая должна быть установлена. Члены `RECT` структуры не определяют ограничивающий прямоугольник. Смотрите [CToolTipCtrl::GetMargin](#getmargin) для описания информации о марже.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_SETMARGIN,](/windows/win32/Controls/ttm-setmargin)как описано в SDK Windows.

## <a name="ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a>CToolTipCtrl::SetMaxTipWidth

Устанавливает максимальную ширину окна наконечника инструмента.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>Параметры

*iWidth*<br/>
Максимальная ширина окна наконечника инструмента, которая будет установлена.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая максимальная ширина наконечника.

### <a name="remarks"></a>Remarks

Эта функция-член реализует поведение сообщения Win32 [TTM_SETMAXTIPWIDTH,](/windows/win32/Controls/ttm-setmaxtipwidth)как описано в SDK Windows.

## <a name="ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a>CToolTipCtrl::SetTipBkColor

Устанавливает цвет фона в окне наконечника инструмента.

```
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Clr*<br/>
Новый цвет фона.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_SETTIPBKCOLOR,](/windows/win32/Controls/ttm-settipbkcolor)как описано в SDK Windows.

## <a name="ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a>CToolTipCtrl::SetTipTextColor

Устанавливает цвет текста в окне наконечника инструмента.

```
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Clr*<br/>
Новый цвет текста.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_SETTIPTEXTCOLOR,](/windows/win32/Controls/ttm-settiptextcolor)как описано в SDK Windows.

## <a name="ctooltipctrlsettitle"></a><a name="settitle"></a>CToolTipCtrl::SetTitle

Добавляет стандартную иконку и строку заголовка к наконечнику инструмента.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>Параметры

*uIcon*<br/>
Смотрите *значок* в [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle) в Windows SDK.

*lpstrTitle*<br/>
Указатель на строку заголовка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TTM_SETTITLE,](/windows/win32/Controls/ttm-settitle)как описано в SDK Windows.

## <a name="ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a>CToolTipCtrl::SetToolInfo

Устанавливает информацию, которую отзыв инструмента поддерживает для инструмента.

```
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>Параметры

*lpToolInfo*<br/>
Указатель на структуру [TOOLINFO,](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) которая определяет информацию для настройки.

## <a name="ctooltipctrlsettoolrect"></a><a name="settoolrect"></a>CToolCtrl::SetToolRect

Устанавливает новый прямоугольник для инструмента.

```
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее инструмент.

*nIDTool*<br/>
Идентификатор инструмента.

*lpRect*<br/>
Указатель на структуру [RECT](/previous-versions/dd162897\(v=vs.85\)) с указанием нового связующего прямоугольника.

## <a name="ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolTipCtrl::SetWindowTheme

Устанавливает визуальный стиль окна наконечника инструмента.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*pszSubAppName*<br/>
Указатель на строку Unicode, содержащую визуальный стиль для настройки.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата не используется.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность [сообщения TTM_SETWINDOWTHEME,](/windows/win32/Controls/ttm-setwindowtheme) как описано в SDK Windows.

## <a name="ctooltipctrlupdate"></a><a name="update"></a>CToolTipCtrl::Обновление

Принуждает текущий инструмент к перерисовке.

```
void Update();
```

## <a name="ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a>CToolCtrl:UpdateTipText

Обновляет текст наконечника инструмента для инструментов этого элемента управления.

```
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указатель на текст для инструмента.

*pWnd*<br/>
Указатель на окно, содержащее инструмент.

*nIDTool*<br/>
Идентификатор инструмента.

*nIDText*<br/>
Идентификатор ресурса строки, содержащий текст для инструмента.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBar](../../mfc/reference/ctoolbar-class.md)
