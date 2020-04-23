---
title: Класс CStatusBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
ms.openlocfilehash: 57d040a7efd87d384e0aaa6275593bc91f38cc86
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753046"
---
# <a name="cstatusbarctrl-class"></a>Класс CStatusBarCtrl

Предоставляет функциональные возможности стандартного элемента управления "индикатор статуса" Windows.

## <a name="syntax"></a>Синтаксис

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStatusBarCtrl:CstatusBarCtrl](#cstatusbarctrl)|Формирует объект `CStatusBarCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStatusBarCtrl::Создание](#create)|Создает элемент управления полосой состояния `CStatusBarCtrl` и прикрепляет его к объекту.|
|[CStatusBarCtrl:CreateEx](#createex)|Создает элемент управления полосой статуса с указанными `CStatusBarCtrl` расширенными стилями Windows и прикрепляет его к объекту.|
|[CStatusBarCtrl::DrawItem](#drawitem)|Вызывается при изменении визуального аспекта управления планкой статуса владельца-рисования.|
|[CStatusBarCtrl:GetBorders](#getborders)|Извлекает текущую ширину горизонтальных и вертикальных границ элемента управления стражей статуса.|
|[CStatusBarCtrl::GetIcon](#geticon)|Извлекает значок для детали (также известной как панель) в текущем элементе управления панели состояния.|
|[CStatusBarCtrl:GetParts](#getparts)|Извлекает количество деталей в элемент управления полосой состояния.|
|[CStatusBarCtrl:GetRect](#getrect)|Извлекает прямоугольник границы детали в элемент управления полосой состояния.|
|[CStatusBarCtrl::GetText](#gettext)|Извлекает текст из данной части элемента управления панели статуса.|
|[CStatusBarCtrl::GetTextДлин](#gettextlength)|Извлеките длину, в символах, текста из данной части управления панели статуса.|
|[CStatusBarCtrl::GetTipText](#gettiptext)|Извлекает текст tooltip для панели в панели состояния.|
|[CStatusBarCtrl::Просто](#issimple)|Проверяетэлементы управления окнами состояния, чтобы определить, находится ли оно в простом режиме.|
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Устанавливает цвет фона в панели статуса.|
|[CStatusBarCtrl::SetIcon](#seticon)|Устанавливает значок для панели в панели состояния.|
|[CStatusBarCtrl:SetMinHeight](#setminheight)|Устанавливает минимальную высоту области рисования элемента управления статусом.|
|[CStatusBarCtrl::SetParts](#setparts)|Устанавливает количество деталей в элемент управления панели состояния и координаты правого края каждой детали.|
|[CStatusBarCtrl::SetSimple](#setsimple)|Определяет, отображает ли элемент управления панелью статуса простой текст или отображает `SetParts`все части управления, установленные предыдущим вызовом.|
|[CStatusBarCtrl::SetText](#settext)|Задает текст в указанной части элемента управления "Строка состояния".|
|[CStatusBarCtrl::SetTipText](#settiptext)|Устанавливает текст инструментария для панели в панели статуса.|

## <a name="remarks"></a>Remarks

"Управление строкой статуса" — это горизонтальное окно, обычно отображаемые в нижней части родительского окна, в котором приложение может отображать различные виды информации о состоянии. Элемент управления панели статуса можно разделить на части для отображения более чем одного типа информации.

Этот элемент управления `CStatusBarCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Для получения дополнительной `CStatusBarCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cstatusbarctrlcreate"></a><a name="create"></a>CStatusBarCtrl::Создание

Создает элемент управления полосой состояния `CStatusBarCtrl` и прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления панелью состояния. Применяйте любую комбинацию стилей управления стражей статуса, перечисленных в [общих стилях управления](/windows/win32/Controls/common-control-styles) в Windows SDK. Этот параметр должен включать WS_CHILD стиль. Он также должен включать в себя WS_VISIBLE стиль.

*rect*<br/>
Определяет размер и положение элемента управления стражей состояния. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Опознавайте родительское окно родительского `CDialog`элемента управления панели статуса, обычно . Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор элемента управления состояния.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Вы строите `CStatusBarCtrl` в два этапа. Сначала позвоните в конструктор, `Create`а затем позвоните, что создает элемент `CStatusBarCtrl` управления полосой состояния и прикрепляет его к объекту.

Положение по умолчанию окна состояния находится в нижней части родительского окна, но можно указать CCS_TOP стиль, чтобы он отображался в верхней части клиентской области родительского окна. Можно указать SBARS_SIZEGRIP стиль, чтобы включить сцепление размеров в правом конце окна статуса. Сочетание CCS_TOP и SBARS_SIZEGRIP стилей не рекомендуется, так как полученное сцепление размеров не является функциональным, даже если система рисует его в окне состояния.

Чтобы создать панель статуса с расширенными стилями окон, позвоните `Create` [cStatusBarCtrl::CreateEx](#createex) вместо .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

## <a name="cstatusbarctrlcreateex"></a><a name="createex"></a>CStatusBarCtrl:CreateEx

Создает элемент управления (детское окно) и `CStatusBarCtrl` связывает его с объектом.

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
Определяет стиль управления панелью состояния. Применяйте любую комбинацию стилей управления стражей статуса, перечисленных в [общих стилях управления](/windows/win32/Controls/common-control-styles) в Windows SDK. Этот параметр должен включать WS_CHILD стиль. Он также должен включать в себя WS_VISIBLE стиль.

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` вместо [создания](#create) для применения расширенных стилей Windows, указанных в предисловии расширенного стиля Windows **WS_EX_.**

## <a name="cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a>CStatusBarCtrl:CstatusBarCtrl

Формирует объект `CStatusBarCtrl`.

```
CStatusBarCtrl();
```

## <a name="cstatusbarctrldrawitem"></a><a name="drawitem"></a>CStatusBarCtrl::DrawItem

Вызывается в рамках, когда визуальный аспект управления положением владельца-рисования панели.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) содержащую информацию о типе требуемого чертежа.

### <a name="remarks"></a>Remarks

Член `itemAction` `DRAWITEMSTRUCT` структуры определяет действие чертежа, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию элемента для `CStatusBarCtrl` реализации чертежа для объекта владельца-рисования.

Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста дисплея, поставляемые в *lpDrawItemStruct,* прежде чем эта функция участника прекратится.

## <a name="cstatusbarctrlgetborders"></a><a name="getborders"></a>CStatusBarCtrl:GetBorders

Извлекает текущую ширину элемента управления состояния горизонтальных и вертикальных границ и пространство между прямоугольниками.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>Параметры

*pГраницы*<br/>
Адрес целого массива с тремя элементами. Первый элемент получает ширину горизонтальной границы, второй получает ширину вертикальной границы, а третий получает ширину границы между прямоугольниками.

*nХорц*<br/>
Ссылка на штат, который получает ширину горизонтальной границы.

*nVert*<br/>
Ссылка на штат, который получает ширину вертикальной границы.

*nSpacing*<br/>
Ссылка на штат, который получает ширину границы между прямоугольниками.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Эти границы определяют расстояние между внешним краем элемента управления и прямоугольниками внутри элемента управления, содержащим текст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

## <a name="cstatusbarctrlgeticon"></a><a name="geticon"></a>CStatusBarCtrl::GetIcon

Извлекает значок для детали (также известной как панель) в текущем элементе управления панели состояния.

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Параметрической детали*|(в) Нулевой индекс части, содержащей значок для извлечения. Если этот параметр -1, то панель статуса считается простой панелью состояния режима.|

### <a name="return-value"></a>Возвращаемое значение

Ручка к значку, если метод удачный; в противном случае, NULL.

### <a name="remarks"></a>Remarks

Этот метод отправляет [SB_GETICON](/windows/win32/Controls/sb-geticon) сообщение, которое описано в SDK Windows.

Контроль панели статуса состоит из ряда текстовых разных стекол, которые также известны как части. Для получения дополнительной информации о панели статуса [Setting the Mode of a CStatusBarCtrl Object](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md) [см.](../../mfc/status-bar-implementation-in-mfc.md)

### <a name="example"></a>Пример

Следующий пример кода определяет `m_statusBar`переменную, которая используется для доступа к текущему элементу управления парами состояния. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>Пример

Следующий пример кода копирует значок на две панели текущего элемента управления полосой состояния. В предыдущем разделе примера кода мы создали элемент управления панели статуса с тремя стеклами, а затем добавили значок к первому стеку. Этот пример извлекает значок из первой панели, а затем добавляет его ко второму и третьему стеку.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

## <a name="cstatusbarctrlgetparts"></a><a name="getparts"></a>CStatusBarCtrl:GetParts

Извлекает количество деталей в элемент управления полосой состояния.

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>Параметры

*nЧастии*<br/>
Количество частей, для которых для получения координат. Если этот параметр превышает количество частей в элементе управления, сообщение получает координаты только для существующих частей.

*pParts*<br/>
Адрес целого массива, имеющего такое же количество элементов, как и количество деталей, указанных *nParts.* Каждый элемент массива получает клиентскую координату правого края соответствующей части. Если элемент установлен на - 1, положение правого края для этой части распространяется на правый край панели статуса.

### <a name="return-value"></a>Возвращаемое значение

Количество частей в элементе управления в случае успеха, или нуля в противном случае.

### <a name="remarks"></a>Remarks

Эта функция члена также получает координаты правого края данного количества частей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

## <a name="cstatusbarctrlgetrect"></a><a name="getrect"></a>CStatusBarCtrl:GetRect

Извлекает прямоугольник границы детали в элемент управления полосой состояния.

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Нулевой индекс части, связывающий прямоугольник которой должен быть извлечен.

*lpRect*<br/>
Адрес структуры [RECT,](/windows/win32/api/windef/ns-windef-rect) которая получает связующий прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

## <a name="cstatusbarctrlgettext"></a><a name="gettext"></a>CStatusBarCtrl::GetText

Извлекает текст из данной части элемента управления панели статуса.

```
CString GetText(
    int nPane,
    int* pType = NULL) const;

int GetText(
    LPCTSTR lpszText,
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Адрес буфера, который получает текст. Этот параметр является нулевой строкой.

*nPane*<br/>
Нулевой индекс детали, из которой можно получить текст.

*pType*<br/>
Указатель на штат, который получает информацию типа. Тип может быть одним из этих значений:

- **0** Текст нарисован с границей для того чтобы появиться более низко чем плоскость адвокатского сословия состояния.

- SBT_NOBORDERS Текст нарисован без границ.

- SBT_POPOUT Текст нарисован с границей, чтобы казаться выше плоскости панели статуса.

- SBT_OWNERDRAW Если текст имеет SBT_OWNERDRAW тип чертежа, *pType* получает это сообщение и возвращает 32-битное значение, связанное с текстом, а не тип длины и операции.

### <a name="return-value"></a>Возвращаемое значение

Длина текста или [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащего текущий текст, в символах.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

## <a name="cstatusbarctrlgettextlength"></a><a name="gettextlength"></a>CStatusBarCtrl::GetTextДлин

Получает длину, в символах, текста из данной части управления панели статуса.

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Нулевой индекс детали, из которой можно получить текст.

*pType*<br/>
Указатель на штат, который получает информацию типа. Тип может быть одним из этих значений:

- **0** Текст нарисован с границей для того чтобы появиться более низко чем плоскость адвокатского сословия состояния.

- SBT_NOBORDERS Текст нарисован без границ.

- SBT_OWNERDRAW Текст нарисован родительским окном.

- SBT_POPOUT Текст нарисован с границей, чтобы казаться выше плоскости панели статуса.

### <a name="return-value"></a>Возвращаемое значение

Длина текста, в символах.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

## <a name="cstatusbarctrlgettiptext"></a><a name="gettiptext"></a>CStatusBarCtrl::GetTipText

Извлекает текст tooltip для панели в панели состояния.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Нулевой индекс панели панели состояния для получения текста tooltip.

### <a name="return-value"></a>Возвращаемое значение

Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий текст, который будет использоваться в наборе инструментов.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [SB_GETTIPTEXT,](/windows/win32/Controls/sb-gettiptext)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

## <a name="cstatusbarctrlissimple"></a><a name="issimple"></a>CStatusBarCtrl::Просто

Проверяетэлементы управления окнами состояния, чтобы определить, находится ли оно в простом режиме.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если управление окнастатусом находится в простом режиме; в противном случае ноль.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [SB_ISSIMPLE,](/windows/win32/Controls/sb-issimple)как описано в SDK Windows.

## <a name="cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a>CStatusBarCtrl::SetBkColor

Устанавливает цвет фона в панели статуса.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Параметры

*Cr*<br/>
Значение COLORREF, которое определяет новый цвет фона. Укажите CLR_DEFAULT значение, чтобы заставить панель статуса использовать свой фоновый цвет по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) представляющее предыдущий цвет фона по умолчанию.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [SB_SETBKCOLOR,](/windows/win32/Controls/sb-setbkcolor)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

## <a name="cstatusbarctrlseticon"></a><a name="seticon"></a>CStatusBarCtrl::SetIcon

Устанавливает значок для панели в панели состояния.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Индекс с нулевым уровнем панели, который получит значок. Если этот параметр -1, то бар статуса считается простой панелью статуса.

*hIcon*<br/>
Ручка к значку, которая будет установлена. Если это значение NULL, значок удаляется из детали.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [SB_SETICON,](/windows/win32/Controls/sb-seticon)как описано в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CStatusBarCtrl::SetBkColor](#setbkcolor).

## <a name="cstatusbarctrlsetminheight"></a><a name="setminheight"></a>CStatusBarCtrl:SetMinHeight

Устанавливает минимальную высоту области рисования элемента управления статусом.

```cpp
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
Минимальная высота, в пикселях, управления.

### <a name="remarks"></a>Remarks

Минимальная высота - это сумма *nMin* и в два раза ширина, в пикселях, вертикальной границы управления полосой статуса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

## <a name="cstatusbarctrlsetparts"></a><a name="setparts"></a>CStatusBarCtrl::SetParts

Устанавливает количество деталей в элемент управления панели состояния и координаты правого края каждой детали.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>Параметры

*nЧастии*<br/>
Количество частей для набора. Количество деталей не может быть больше 255.

*pWidths*<br/>
Адрес целого массива, имеющего такое же количество элементов, как и частей, указанных *nParts.* Каждый элемент массива определяет положение в координатах клиента правого края соответствующей части. Если элемент - 1, то положение правого края для этой части простирается до правого края элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

## <a name="cstatusbarctrlsetsimple"></a><a name="setsimple"></a>CStatusBarCtrl::SetSimple

Определяет, отображает ли элемент управления панелью статуса простой текст или отображает все части управления, установленные предыдущим вызовом [в SetParts.](#setparts)

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>Параметры

*bПростой*<br/>
(в) Флаг типа дисплея. Если этот параметр является правдой, элемент управления отображает простой текст; если это FALSE, он отображает несколько частей.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 0.

### <a name="remarks"></a>Remarks

Если приложение изменяет элемент управления панели статуса с непростого на простой или наоборот, система немедленно перерисовывает элемент управления.

## <a name="cstatusbarctrlsettext"></a><a name="settext"></a>CStatusBarCtrl::SetText

Задает текст в указанной части элемента управления "Строка состояния".

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Адрес в виде оканчивающейся нулем строки, в которой указан необходимый текст. Если *nType* SBT_OWNERDRAW, *lpszText* представляет 32 бита данных.

*nPane*<br/>
Отсчитываемый от нуля индекс настраиваемой части. Если это значение равно 255, строка состояния считается простым элементом управления, состоящим из одной части.

*nType*<br/>
Тип операции отрисовки. Список возможных значений [смотрите SB_SETTEXT сообщение.](/windows/win32/Controls/sb-settext)

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Сообщение аннулирует измененную часть элемента управления, в результате чего он отображает новый текст при следующем элементе управления, который получает WM_PAINT сообщение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

## <a name="cstatusbarctrlsettiptext"></a><a name="settiptext"></a>CStatusBarCtrl::SetTipText

Устанавливает текст инструментария для панели в панели статуса.

```cpp
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Нулевой индекс панели панели состояния для получения текста tooltip.

*pszTipText*<br/>
Указатель на строку, содержащую текст tooltip.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [SB_SETTIPTEXT,](/windows/win32/Controls/sb-settiptext)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)
