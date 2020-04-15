---
title: Класс CReBarCtrl
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: 776892d71e2cb0f5d57512754cd7fa12730eb044
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367447"
---
# <a name="crebarctrl-class"></a>Класс CReBarCtrl

Инкапсулирует функциональность элемента управления "главная панель ", который представляет собой контейнер для дочернего окна.

## <a name="syntax"></a>Синтаксис

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кребарктор:Кребарктор](#crebarctrl)|Формирует объект `CReBarCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кребарктрл:Бегиндраг](#begindrag)|Размещайте элемент управления арматом в режим перетаскивания.|
|[CRebarCtrl::Создание](#create)|Создает элемент управления арматом и `CReBarCtrl` прикрепляет его к объекту.|
|[Кребарктр::CreateEx](#createex)|Создает элемент управления арматорной армате с указанными `CReBarCtrl` расширенными стилями Windows и прикрепляет его к объекту.|
|[CReBarCtrl::DeleteBand](#deleteband)|Удаляет полосу из элемента управления арматом.|
|[Кребаркторл::DragMove](#dragmove)|Обновляет положение перетаскивания в элементе `BeginDrag`управления арматом после вызова.|
|[Кребарктрл::Энддраг](#enddrag)|Прекращает операцию управления ребартом перетаскивания и падения.|
|[Кребаркторль::GetBandBorders](#getbandborders)|Извлекает границы полосы.|
|[Кребаркторль:ГетбандКтль](#getbandcount)|Получает количество полос, наиболее наиболее наивных полос, наданных в настоящее время.|
|[Кребарктр::ГетбандИнфо](#getbandinfo)|Извлекает информацию об указанной полосе в элементе управления арматом.|
|[CReBarCtrl:GetBandMargins](#getbandmargins)|Извлекает поля полосы.|
|[Кребаркторль::GetBarHeight](#getbarheight)|Извлекает высоту арматы.|
|[Кребарктр::Гетбаринфо](#getbarinfo)|Получает информацию о элементе управления арматом и списке изображений, который она использует.|
|[Кребаркторль::GetBkColor](#getbkcolor)|Получает цвет фона управления арматрией по умолчанию.|
|[Кребарктр:ГетколорСхема](#getcolorscheme)|Извлекает структуру [COLORSCHEME,](/windows/win32/api/commctrl/ns-commctrl-colorscheme) связанную с контролем арматы.|
|[Кребаркторль::GetDropTarget](#getdroptarget)|Извлекает указатель интерфейса `IDropTarget` управления армате.|
|[Кребарктрл:GetExtendedStyle](#getextendedstyle)|Получает расширенный стиль текущего управления арматом.|
|[Кребарктр::GetImagelist](#getimagelist)|Извлекает список изображений, связанный с управлением арматом.|
|[Кребарктрл:Гетпалпалпал](#getpalette)|Извлекает текущую палитру управления армате.|
|[Кребарктр::GetRect](#getrect)|Извлекает прямоугольник для данной полосы в арматр-контроле.|
|[Кребаркторль::Гетроуктом](#getrowcount)|Извлекает количество строк полосы в элементе управления арматом.|
|[Кребаркторль::Высота](#getrowheight)|Извлекает высоту заданного ряда в армате управления.|
|[Кребарктр::GetTextColor](#gettextcolor)|Извлекает цвет текста управления арматрией по умолчанию.|
|[Кребаркторль::GetToolTips](#gettooltips)|Извлекает ручку на любой элемент управления наконечником инструмента, связанный с управлением арматом.|
|[Кребарктрл:Хиттест](#hittest)|Определяет, какая часть армательной полосы находится в данной точке на экране, если в этот момент существует полоса арматы.|
|[Кребарктр:IDToIndex](#idtoindex)|Преобразует идентификатор полосы (ID) в индекс полосы в элементе управления арматом.|
|[Кребарктрл:Вставить](#insertband)|Вставляет новую полосу в армазный элемент.|
|[Кребаркторль::МаксимикБанд](#maximizeband)|Изобрезирует полосу в арматорном управлении до ее самого большого размера.|
|[Кребарктрл:Минимизация](#minimizeband)|Изобрезирует полосу в арматорном элементе управления до ее наименьшего размера.|
|[Кребаркторль::Движение](#moveband)|Перемещает полосу из одного индекса в другой.|
|[Кребарктр::Pушшеврон](#pushchevron)|Программно толкает шеврон.|
|[Кребаркторль::Восстановление](#restoreband)|Изобрезирует полосу в арматорном управлении до идеального размера.|
|[Кребарктр::SetBandInfo](#setbandinfo)|Устанавливает характеристики существующей полосы в элементе управления армаброй.|
|[Кребаркторль::SetBandWidth](#setbandwidth)|Устанавливает ширину указанной пристыкованой полосы в текущем элементе управления арматом.|
|[Кребарктр::СетБарИнфо](#setbarinfo)|Устанавливает характеристики арматы управления.|
|[Кребаркторль::SetBkColor](#setbkcolor)|Устанавливает цвет фона управления арматрией по умолчанию.|
|[Кребаркторль::SetcolorScheme](#setcolorscheme)|Устанавливает цветовую схему для кнопок на элементе управления армаброй.|
|[Кребарктрл:SetExtendedStyle](#setextendedstyle)|Устанавливает расширенные стили для текущего управления арматом.|
|[Кребарктр::SetImagelist](#setimagelist)|Устанавливает список изображений управления арматом.|
|[Кребаркторль::Владелец](#setowner)|Устанавливает окно владельца управления армате.|
|[Кребарктрл::SetPalette](#setpalette)|Устанавливает текущую палитру управления арматом.|
|[Кребаркторль::SetTextColor](#settextcolor)|Устанавливает цвет текста управления арматрией по умолчанию.|
|[Кребаркторль::SetToolTips](#settooltips)|Associates инструмент отзыв управления с арматом управления.|
|[Кребарктр::SetWindowTheme](#setwindowtheme)|Устанавливает визуальный стиль управления арматом.|
|[Кребаркторль::ShowBand](#showband)|Показывает или скрывает данную полосу в армате управления.|
|[Кребарктор::SizeToRect](#sizetorect)|Подходит для управления арматом к указанному прямоугольнику.|

## <a name="remarks"></a>Remarks

Приложение, в котором находится элемент управления арматом, присваивает детское окно, содержащееся в элементе управления арматом, полосе арматы. Окно ребенка, как правило, еще один общий контроль.

Элементы управления ребарами содержат одну или несколько полос. Каждая полоса может содержать комбинацию панели захвата, бит-карты, текстовой метки и детского окна. Полоса может содержать только один из этих элементов.

Элемент управления арматом может отображать оконное окно ребенка на заданной фоновой битовой карте. Все полосы управления арматом могут быть уменьшены, за исключением тех, которые используют RBBS_FIXEDSIZE стиль. При перемещении или пересчете полосы управления арматом управление армаровой резинкой управляет размером и положением окна ребенка, назначенного этой полосе. Чтобы изменить размер или изменить порядок полос в пределах управления, нажмите и перетащите сцепление бар полосы.

На следующей иллюстрации показан контроль арматы, который имеет три полосы:

- Band 0 содержит плоский, прозрачный элемент управления панелью инструментов.

- Группа 1 содержит как прозрачные стандартные, так и прозрачные кнопки выпадения.

- Band 2 содержит комбо-коробку и четыре стандартные кнопки.

   ![Пример меню "Главная панель"](../../mfc/reference/media/vc4scc1.gif "Пример меню "Главная панель"")

## <a name="rebar-control"></a>Контроль ребара

Поддержка управления ребарами:

- Списки изображений.

- Обработка сообщений.

- Пользовательская функция рисования.

- Разнообразие стилей управления в дополнение к стандартным стилям окна. Список этих стилей можно узнать в [SDK](/windows/win32/Controls/rebar-control-styles) Windows.

Для получения дополнительной информации [см.](../../mfc/using-crebarctrl.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="crebarctrlbegindrag"></a><a name="begindrag"></a>Кребарктрл:Бегиндраг

Реализует поведение сообщения Win32 [RB_BEGINDRAG,](/windows/win32/Controls/rb-begindrag)как описано в SDK Windows.

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс диапазона, на который повлияет операция перетаскивания и падения.

*dwPos*<br/>
Значение DWORD, содержащее координаты исходной мыши. Горизонтальная координата содержится в LOWORD, а вертикальная координат – в HIWORD. Если вы проходите (DWORD)-1, управление армаровой армате будет использовать положение `GetMessage` мыши `PeekMessage`в последний раз, когда поток управления называется или .

## <a name="crebarctrlcreate"></a><a name="create"></a>CRebarCtrl::Создание

Создает элемент управления арматом и `CReBarCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет сочетание стилей управления арматом, применяемых к управлению. В списке поддерживаемых стилей с [милисот-контролем rebar](/windows/win32/Controls/rebar-control-styles) можно ознакомиться в SDK Windows.

*rect*<br/>
Ссылка на объект [CRect](../../atl-mfc-shared/reference/crect-class.md) или структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) которая является положением и размером управления арматром.

*pParentWnd*<br/>
Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном управления арматом. Она не должна быть NULL.

*nID*<br/>
Уведомляет идентификатор управления армате.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект был создан успешно; в противном случае 0.

### <a name="remarks"></a>Remarks

Создание управления арматом в два этапа:

1. Позвоните `CReBarCtrl` [CReBarCtrl,](#crebarctrl) чтобы построить объект.

1. Вызов исвызывайте эту функцию участника, которая создает `CReBarCtrl` управление арматорной арматой Windows и прикрепляет его к объекту.

При вызове `Create`общие элементы управления инициализированы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

## <a name="crebarctrlcreateex"></a><a name="createex"></a>Кребарктр::CreateEx

Создает элемент управления (детское окно) и `CReBarCtrl` связывает его с объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Определяет сочетание стилей управления арматом, применяемых к управлению. Список поддерживаемых стилей можно узнать в [SDK](/windows/win32/Controls/rebar-control-styles) Windows.

*rect*<br/>
Ссылка на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` вместо [создания](#create) для применения расширенных стилей Windows, указанных в предисловии расширенного стиля Windows **WS_EX_.**

## <a name="crebarctrlcrebarctrl"></a><a name="crebarctrl"></a>Кребарктор:Кребарктор

Создает объект `CReBarCtrl`.

```
CReBarCtrl();
```

### <a name="example"></a>Пример

  Смотрите пример [для CReBarCtrl::Создание](#create).

## <a name="crebarctrldeleteband"></a><a name="deleteband"></a>CReBarCtrl::DeleteBand

Реализует поведение сообщения Win32 [RB_DELETEBAND,](/windows/win32/Controls/rb-deleteband)как описано в SDK Windows.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы, который будет удален.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если полоса удалена успешно; в противном случае ноль.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

## <a name="crebarctrldragmove"></a><a name="dragmove"></a>Кребаркторл::DragMove

Реализует поведение сообщения Win32 [RB_DRAGMOVE,](/windows/win32/Controls/rb-dragmove)как описано в SDK Windows.

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Параметры

*dwPos*<br/>
Значение DWORD, содержащее новые координаты мыши. Горизонтальная координата содержится в LOWORD, а вертикальная координат – в HIWORD. Если вы проходите (DWORD)-1, управление армаровой армате будет использовать положение `GetMessage` мыши `PeekMessage`в последний раз, когда поток управления называется или .

## <a name="crebarctrlenddrag"></a><a name="enddrag"></a>Кребарктрл::Энддраг

Реализует поведение сообщения Win32 [RB_ENDDRAG,](/windows/win32/Controls/rb-enddrag)как описано в SDK Windows.

```
void EndDrag();
```

## <a name="crebarctrlgetbandborders"></a><a name="getbandborders"></a>Кребаркторль::GetBandBorders

Реализует поведение сообщения Win32 [RB_GETBANDBORDERS,](/windows/win32/Controls/rb-getbandborders)как описано в SDK Windows.

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы, для которого будут восстановлены границы.

*Кнр*<br/>
Указатель на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) которая получит границы полосы. Если управление арматом имеет RBS_BANDBORDERS стиль, каждый член этой структуры получит количество пикселей, на соответствующей стороне полосы, которые составляют границу. Если элемент управления арматом не имеет RBS_BANDBORDERS стиля, только левый член этой структуры получает достоверные сведения. Для описания стилей управления арматом [см.](/windows/win32/Controls/rebar-control-styles)

## <a name="crebarctrlgetbandcount"></a><a name="getbandcount"></a>Кребаркторль:ГетбандКтль

Реализует поведение сообщения Win32 [RB_GETBANDCOUNT,](/windows/win32/Controls/rb-getbandcount)как описано в SDK Windows.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество полос, назначенных для управления.

## <a name="crebarctrlgetbandinfo"></a><a name="getbandinfo"></a>Кребарктр::ГетбандИнфо

Реализует поведение сообщения Win32 [RB_GETBANDINFO,](/windows/win32/Controls/rb-getbandinfo) как описано в SDK Windows.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс диапазона, для которого информация будет получена.

*prbbi*<br/>
Указатель на структуру [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) для получения информации о группе. Перед отправкой `cbSize` этого сообщения `sizeof(REBARBANDINFO)` необходимо настроить `fMask` участника этой структуры и настроить его к элементам, которые вы хотите получить.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlgetbandmargins"></a><a name="getbandmargins"></a>CReBarCtrl:GetBandMargins

Извлекает поля полосы.

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Параметры

*pMargins*<br/>
Указатель на структуру [MARGINS,](/windows/win32/api/uxtheme/ns-uxtheme-margins)которая будет получать информацию.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность [RB_GETBANDMARGINS](/windows/win32/Controls/rb-getbandmargins) сообщения, как описано в SDK Windows.

## <a name="crebarctrlgetbarheight"></a><a name="getbarheight"></a>Кребаркторль::GetBarHeight

Получает высоту армата бар.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, представляющее высоту, в пикселях, элемента управления.

## <a name="crebarctrlgetbarinfo"></a><a name="getbarinfo"></a>Кребарктр::Гетбаринфо

Реализует поведение сообщения Win32 [RB_GETBARINFO,](/windows/win32/Controls/rb-getbarinfo)как описано в SDK Windows.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Параметры

*prbi*<br/>
Указатель на структуру [REBARINFO,](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) которая будет получать информацию о контроле за армабаром. Перед отправкой этого сообщения необходимо `sizeof(REBARINFO)` настроить член *cbSize* этой структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlgetbkcolor"></a><a name="getbkcolor"></a>Кребаркторль::GetBkColor

Реализует поведение сообщения Win32 [RB_GETBKCOLOR,](/windows/win32/Controls/rb-getbkcolor)как описано в SDK Windows.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее текущий цвет фона по умолчанию.

## <a name="crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>Кребарктр:ГетколорСхема

Извлекает структуру [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) для управления армазой.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Параметры

*lpcs*<br/>
Указатель на структуру [COLORSCHEME,](/windows/win32/api/commctrl/ns-commctrl-colorscheme) как описано в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Структура `COLORSCHEME` включает в себя цвет кнопки выделить и цвет тени кнопки.

## <a name="crebarctrlgetdroptarget"></a><a name="getdroptarget"></a>Кребаркторль::GetDropTarget

Реализует поведение сообщения Win32 [RB_GETDROPTARGET,](/windows/win32/Controls/rb-getdroptarget)как описано в SDK Windows.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс [IDropTarget.](/windows/win32/api/oleidl/nn-oleidl-idroptarget)

## <a name="crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>Кребарктрл:GetExtendedStyle

Получает расширенные стили текущего управления арматом.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Битовая комбинация (ИЛИ) флагов, указывающих на расширенные стили. Возможные флаги RBS_EX_SPLITTER и RBS_EX_TRANSPARENT. Для получения дополнительной *dwMask* информации см. [CReBarCtrl::SetExtendedStyle](#setextendedstyle)

### <a name="remarks"></a>Remarks

Этот метод отправляет [RB_GETEXTENDEDSTYLE](/windows/win32/Controls/rb-dragmove) сообщение, которое описано в SDK Windows.

## <a name="crebarctrlgetimagelist"></a><a name="getimagelist"></a>Кребарктр::GetImagelist

Получает `CImageList` объект, связанный с контролем арматы.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList.](../../mfc/reference/cimagelist-class.md) Возвращает NULL, если для элемента управления не установлен список изображений.

### <a name="remarks"></a>Remarks

Эта функция-член использует информацию о размере и маске, хранящуюся в структуре [REBARINFO,](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) как описано в SDK Windows.

## <a name="crebarctrlgetpalette"></a><a name="getpalette"></a>Кребарктрл:Гетпалпалпал

Извлекает текущую палитру управления армате.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CPalette](../../mfc/reference/cpalette-class.md) с указанием текущей палитры управления арматром.

### <a name="remarks"></a>Remarks

Обратите внимание, что `CPalette` эта функция члена использует объект в качестве значения возврата, а не Hpalette.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

## <a name="crebarctrlgetrect"></a><a name="getrect"></a>Кребарктр::GetRect

Реализует поведение сообщения Win32 [RB_GETRECT,](/windows/win32/Controls/rb-getrect)как описано в SDK Windows.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы в элементе управления арматом.

*Кнр*<br/>
Указатель на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) которая получит границы арматорной полосы.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

## <a name="crebarctrlgetrowcount"></a><a name="getrowcount"></a>Кребаркторль::Гетроуктом

Реализует поведение сообщения Win32 [RB_GETROWCOUNT,](/windows/win32/Controls/rb-getrowcount)как описано в SDK Windows.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение UINT, представляющее количество строк полосы в элементе управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

## <a name="crebarctrlgetrowheight"></a><a name="getrowheight"></a>Кребаркторль::Высота

Реализует поведение сообщения Win32 [RB_GETROWHEIGHT,](/windows/win32/Controls/rb-getrowheight)как описано в SDK Windows.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Параметры

*uRow*<br/>
Нулевой индекс полосы, который будет иметь свою высоту извлечены.

### <a name="return-value"></a>Возвращаемое значение

Значение UINT, представляющее высоту строки, в пикселях.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

## <a name="crebarctrlgettextcolor"></a><a name="gettextcolor"></a>Кребарктр::GetTextColor

Реализует поведение сообщения Win32 [RB_GETTEXTCOLOR,](/windows/win32/Controls/rb-gettextcolor)как описано в SDK Windows.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее текущий цвет текста по умолчанию.

## <a name="crebarctrlgettooltips"></a><a name="gettooltips"></a>Кребаркторль::GetToolTips

Реализует поведение сообщения Win32 [RB_GETTOOLTIPS,](/windows/win32/Controls/rb-gettooltips)как описано в SDK Windows.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CToolTipCtrl.](../../mfc/reference/ctooltipctrl-class.md)

### <a name="remarks"></a>Remarks

Обратите внимание, что `GetToolTips` реализация MFC возвращает `CToolTipCtrl`указатель на, а не HWND.

## <a name="crebarctrlhittest"></a><a name="hittest"></a>Кребарктрл:Хиттест

Реализует поведение сообщения Win32 [RB_HITTEST,](/windows/win32/Controls/rb-hittest)как описано в SDK Windows.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Параметры

*prbht*<br/>
Указатель на структуру [RBHITTESTINFO.](/windows/win32/api/commctrl/ns-commctrl-rbhittestinfo) Перед отправкой `pt` сообщения, член этой структуры должен быть инициализирован до точки, которая будет протестирована, в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Индекс диапазона с нулевым уровнем в данной точке или -1, если в точке не было полосы арматы.

## <a name="crebarctrlidtoindex"></a><a name="idtoindex"></a>Кребарктр:IDToIndex

Реализует поведение сообщения Win32 [RB_IDTOINDEX,](/windows/win32/controls/rb-idtoindex)как описано в SDK Windows.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Параметры

*uBandID*<br/>
Идентификатор приложения указанной полосы, `wID` переданный в составе структуры [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) при вставке.

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой полосы в случае успеха или -1 в противном случае. При наличии дубликатов индексов диапазона возвращается первый.

## <a name="crebarctrlinsertband"></a><a name="insertband"></a>Кребарктрл:Вставить

Реализует поведение сообщения Win32 [RB_INSERTBAND,](/windows/win32/Controls/rb-insertband)как описано в SDK Windows.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Параметры

*uИндекс*<br/>
Нулевой индекс местоположения, где будет вставлена полоса. Если вы установите этот параметр до -1, элемент управления добавит новую полосу в последнем месте.

*prbbi*<br/>
Указатель на структуру [REBARBANDINFO,](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) определяющую вставку полосы. Прежде `sizeof(REBARBANDINFO)` чем вызывать эту функцию, необходимо настроить член *cbSize* этой структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

## <a name="crebarctrlmaximizeband"></a><a name="maximizeband"></a>Кребаркторль::МаксимикБанд

Изобрезирует полосу в арматорном управлении до ее самого большого размера.

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы, который будет максимально.

### <a name="remarks"></a>Remarks

Реализует поведение сообщения Win32 [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) `fIdeal` с набором до 0, как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

## <a name="crebarctrlminimizeband"></a><a name="minimizeband"></a>Кребарктрл:Минимизация

Изобрезирует полосу в арматорном элементе управления до ее наименьшего размера.

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы должен быть сведен к минимуму.

### <a name="remarks"></a>Remarks

Реализует поведение сообщения Win32 [RB_MINIMIZEBAND,](/windows/win32/Controls/rb-minimizeband)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

## <a name="crebarctrlmoveband"></a><a name="moveband"></a>Кребаркторль::Движение

Реализует поведение сообщения Win32 [RB_MOVEBAND,](/windows/win32/Controls/rb-moveband)как описано в SDK Windows.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Параметры

*uFrom*<br/>
Нулевой индекс полосы, который будет перемещен.

*Ото*<br/>
Нулевой индекс новой позиции диапазона. Значение этого параметра никогда не должно быть больше, чем количество полос минус один. Чтобы получить количество полос, позвоните [в GetBandCount](#getbandcount).

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlpushchevron"></a><a name="pushchevron"></a>Кребарктр::Pушшеврон

Реализует поведение сообщения Win32 [RB_PUSHCHEVRON,](/windows/win32/Controls/rb-pushchevron)как описано в SDK Windows.

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс группы, шеврон которой должен быть толкнул.

*lAppValue*<br/>
Приложение определило 32-битное значение. Смотрите *lAppValue* в [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron) в SDK Windows.

## <a name="crebarctrlrestoreband"></a><a name="restoreband"></a>Кребаркторль::Восстановление

Изобрезирует полосу в арматорном управлении до идеального размера.

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы, который будет максимально.

### <a name="remarks"></a>Remarks

Реализует поведение сообщения Win32 [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) `fIdeal` с набором до 1, как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

## <a name="crebarctrlsetbandinfo"></a><a name="setbandinfo"></a>Кребарктр::SetBandInfo

Реализует поведение сообщения Win32 [RB_SETBANDINFO,](/windows/win32/Controls/rb-setbandinfo)как описано в SDK Windows.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы для получения новых настроек.

*prbbi*<br/>
Указатель на структуру [REBARBANDINFO,](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) определяющую вставку полосы. Перед отправкой `cbSize` этого сообщения `sizeof(REBARBANDINFO)` необходимо настроить члена этой структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

## <a name="crebarctrlsetbandwidth"></a><a name="setbandwidth"></a>Кребаркторль::SetBandWidth

Устанавливает ширину указанной пристыкованой полосы в текущем элементе управления арматом.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*uBand*|(в) Нулевой индекс армата.|
|*cxВимизм*|(в) Новая ширина армата, в пикселях.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод успешен; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [RB_SETBANDWIDTH](/windows/win32/Controls/rb-setbandwidth) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_rebar`переменную, которая используется для доступа к текущему элементу управления арматом. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает каждую полосу арматы, чтобы быть одинаковой шириной.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

## <a name="crebarctrlsetbarinfo"></a><a name="setbarinfo"></a>Кребарктр::СетБарИнфо

Реализует поведение сообщения Win32 [RB_SETBARINFO,](/windows/win32/Controls/rb-setbarinfo)как описано в SDK Windows.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Параметры

*prbi*<br/>
Указатель на структуру [REBARINFO,](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) содержащую информацию, подкоторойпрочную. Вы должны `cbSize` установить член `sizeof(REBARINFO)` этой структуры, прежде чем отправлять это сообщение

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

## <a name="crebarctrlsetbkcolor"></a><a name="setbkcolor"></a>Кребаркторль::SetBkColor

Реализует поведение сообщения Win32 [RB_SETBKCOLOR,](/windows/win32/Controls/rb-setbkcolor)как описано в SDK Windows.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Clr*<br/>
Значение COLORREF, представляющее новый цвет фона по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) представляющее предыдущий цвет фона по умолчанию.

### <a name="remarks"></a>Remarks

Дополнительную информацию о том, когда установить цвет фона и как установить значение значения по умолчанию, читайте в этой теме.

## <a name="crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>Кребаркторль::SetcolorScheme

Устанавливает цветовую схему для кнопок на элементе управления армаброй.

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Параметры

*lpcs*<br/>
Указатель на структуру [COLORSCHEME,](/windows/win32/api/commctrl/ns-commctrl-colorscheme) как описано в SDK Windows.

### <a name="remarks"></a>Remarks

Структура `COLORSCHEME` включает в себя как цвет кнопки выделить и цвет тени кнопки.

## <a name="crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>Кребарктрл:SetExtendedStyle

Устанавливает расширенные стили для текущего управления арматом.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwMask*|(в) Битовая комбинация (ИЛИ) флагов, указывающих, какие флаги в параметре *dwStyleEx* применяются. Используйте одно или несколько из следующих значений:<br /><br /> RBS_EX_SPLITTER: по умолчанию покажите сплиттер внизу в горизонтальном режиме и вправо в вертикальном режиме.<br /><br /> RBS_EX_TRANSPARENT: Перенаправить [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) сообщение в родительское окно.|
|*dwStyleEx*|(в) Битовая комбинация (ИЛИ) флагов, определяющих стили для применения. Чтобы установить стиль, укажите тот же флаг, который используется в параметре *dwMask.* Чтобы сбросить стиль, укажите двоичный ноль.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий расширенный стиль.

### <a name="remarks"></a>Remarks

Этот метод отправляет [RB_SETEXTENDEDSTYLE](/windows/win32/Controls/rb-setextendedstyle) сообщение, которое описано в SDK Windows.

## <a name="crebarctrlsetimagelist"></a><a name="setimagelist"></a>Кребарктр::SetImagelist

Присваивая список изображений элементу управления армате.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*pImageList*<br/>
Указатель на объект [CImageList,](../../mfc/reference/cimagelist-class.md) содержащий список изображений, который будет назначен элементу управления арматом.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlsetowner"></a><a name="setowner"></a>Кребаркторль::Владелец

Реализует поведение сообщения Win32 [RB_SETPARENT,](/windows/win32/Controls/rb-setparent)как описано в SDK Windows.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на `CWnd` объект, установленный в качестве владельца элемента управления арматом.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является текущим владельцем элемента управления арматом.

### <a name="remarks"></a>Remarks

Обратите внимание, что эта `CWnd` функция элемента использует указатели на объекты как для текущего, так и для выбранного владельца управления арматом, а не ручки к окнам.

> [!NOTE]
> Эта функция элемента не изменяет фактический родительский элемент, который был установлен при создании элемента управления; скорее он отправляет уведомления в указанное окно.

## <a name="crebarctrlsetpalette"></a><a name="setpalette"></a>Кребарктрл::SetPalette

Реализует поведение сообщения Win32 [RB_SETPALETTE,](/windows/win32/Controls/rb-setpalette)как описано в SDK Windows.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Параметры

*hPal*<br/>
Hpalette, который определяет новую палитру, что контроль арматы будет использовать.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CPalette](../../mfc/reference/cpalette-class.md) с указанием предыдущей палитры управления арматром.

### <a name="remarks"></a>Remarks

Обратите внимание, что `CPalette` эта функция члена использует объект в качестве значения возврата, а не Hpalette.

## <a name="crebarctrlsettextcolor"></a><a name="settextcolor"></a>Кребаркторль::SetTextColor

Реализует поведение сообщения Win32 [RB_SETTEXTCOLOR,](/windows/win32/Controls/rb-settextcolor)как описано в SDK Windows.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Clr*<br/>
Значение COLORREF, представляющее новый `CReBarCtrl` цвет текста в объекте.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) представляющее предыдущий цвет `CReBarCtrl` текста, связанный с объектом.

### <a name="remarks"></a>Remarks

Он предоставляется для поддержки гибкости цвета текста в арматрии управления.

## <a name="crebarctrlsettooltips"></a><a name="settooltips"></a>Кребаркторль::SetToolTips

Associates инструмент отзыв управления с арматом управления.

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Параметры

*pToolTip*<br/>
Указатель на объект [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

### <a name="remarks"></a>Remarks

Вы должны `CToolTipCtrl` уничтожить объект, когда вы закончите с ним.

## <a name="crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>Кребарктр::SetWindowTheme

Устанавливает визуальный стиль управления арматом.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*pszSubAppName*<br/>
Указатель на строку Unicode, которая содержит визуальный стиль арматы для установки.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата не используется.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность [RB_SETWINDOWTHEME](/windows/win32/Controls/rb-setwindowtheme) сообщения, как описано в SDK Windows.

## <a name="crebarctrlshowband"></a><a name="showband"></a>Кребаркторль::ShowBand

Реализует поведение сообщения Win32 [RB_SHOWBAND,](/windows/win32/Controls/rb-showband)как описано в SDK Windows.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Параметры

*uBand*<br/>
Нулевой индекс полосы в элементе управления арматом.

*fShow*<br/>
Указывает, должна ли полоса быть показана или скрыта. Если это значение соответствует действительности, группа будет показана. В противном случае, группа будет скрыта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

## <a name="crebarctrlsizetorect"></a><a name="sizetorect"></a>Кребарктор::SizeToRect

Реализует поведение сообщения Win32 [RB_SIZETORECT,](/windows/win32/Controls/rb-sizetorect)как описано в SDK Windows.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Ссылка на объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) который определяет прямоугольник, размер управления арматом должен быть размером с.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Обратите внимание, что `CRect` эта функция члена использует `RECT` объект в качестве параметра, а не структуры.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
