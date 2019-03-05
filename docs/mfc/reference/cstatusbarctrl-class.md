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
ms.openlocfilehash: 5a5adc5ae6b1981d7f8260d684a33d8bd7918e40
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272845"
---
# <a name="cstatusbarctrl-class"></a>Класс CStatusBarCtrl

Предоставляет функциональные возможности стандартного элемента управления "индикатор статуса" Windows.

## <a name="syntax"></a>Синтаксис

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Создает объект `CStatusBarCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStatusBarCtrl::Create](#create)|Создает элемент управления строка состояния и присоединяет его к `CStatusBarCtrl` объекта.|
|[CStatusBarCtrl::CreateEx](#createex)|Создает элемент управления строка состояния с указанного расширенные стили Windows и присоединяет его к `CStatusBarCtrl` объекта.|
|[CStatusBarCtrl::DrawItem](#drawitem)|Вызывается при изменении внешнего вида панели управления рисуемого владельцем состояние изменится.|
|[CStatusBarCtrl::GetBorders](#getborders)|Извлекает текущей ширины горизонтальной и вертикальной границы строки состояния.|
|[CStatusBarCtrl::GetIcon](#geticon)|Получает значок для элемента (также известный как панель) строки состояния.|
|[CStatusBarCtrl::GetParts](#getparts)|Получает количество частей строки состояния.|
|[CStatusBarCtrl::GetRect](#getrect)|Возвращает ограничивающий прямоугольник части строки состояния.|
|[CStatusBarCtrl::GetText](#gettext)|Получение текста из указанной части элемента управления строка состояния.|
|[CStatusBarCtrl::GetTextLength](#gettextlength)|Получите длина в символах текста из указанной части элемента управления строка состояния.|
|[CStatusBarCtrl::GetTipText](#gettiptext)|Извлекает текст подсказки для панели строки состояния.|
|[CStatusBarCtrl::IsSimple](#issimple)|Проверяет элемент управления окна состояния, чтобы определить, является ли он в простом режиме.|
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Задает цвет фона в строке состояния.|
|[CStatusBarCtrl::SetIcon](#seticon)|Задает значок для области в строке состояния.|
|[CStatusBarCtrl::SetMinHeight](#setminheight)|Задает минимальную высоту состояние панели области рисования элемента управления.|
|[CStatusBarCtrl::SetParts](#setparts)|Задает число частей в строке элемента управления и координата правого края каждая часть состояния.|
|[CStatusBarCtrl::SetSimple](#setsimple)|Определяет, отображает простой текст строки состояния или отображает все части элемента управления, заданные предыдущим вызовом `SetParts`.|
|[CStatusBarCtrl::SetText](#settext)|Задает текст в указанной части элемента управления "Строка состояния".|
|[CStatusBarCtrl::SetTipText](#settiptext)|Задает текст подсказки для панели строки состояния.|

## <a name="remarks"></a>Примечания

Элемент «управления строка состояния» является окном, горизонтальная, обычно отображается в нижней части родительского окна, в которой выводятся различные сведения о состоянии приложения. Строки состояния можно разделить на отдельные части для отображения более чем один тип данных.

Этот элемент управления (и, следовательно `CStatusBarCtrl` класс) доступны только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних версиях.

Дополнительные сведения об использовании `CStatusBarCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="create"></a>  CStatusBarCtrl::Create

Создает элемент управления строка состояния и присоединяет его к `CStatusBarCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль управления строкой состояния. Применить любое сочетание строки стили элемента управления, перечисленные в состояния [общие стили элемента управления](/windows/desktop/Controls/common-control-styles) в пакете Windows SDK. Этот параметр должен содержать стиль WS_CHILD. Она также должна включать WS_VISIBLE стиль.

*rect*<br/>
Задает размер и положение управления строкой состояния. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.

*pParentWnd*<br/>
Указывает состояние панели родительскому окну элемента управления, обычно `CDialog`. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор управления строкой состояния.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CStatusBarCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает строки состояния и присоединяет его к `CStatusBarCtrl` объекта.

Позиция по умолчанию состояние окна находится в нижней части родительского окна, но вы можете указать стиль CCS_TOP, чтобы они появились в верхней части клиентской области родительского окна. Можно указать стиль SBARS_SIZEGRIP, добавляя захват для изменения размера в правом конце окна состояния. Объединение CCS_TOP и SBARS_SIZEGRIP стили не рекомендуется, поскольку полученный Захват регулировки размера не работает, несмотря на то, что система отображает его в окне состояния.

Чтобы создать строку состояния с расширенные стили окна, вызовите [CStatusBarCtrl::CreateEx](#createex) вместо `Create`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

##  <a name="createex"></a>  CStatusBarCtrl::CreateEx

Создает элемент управления (дочернего окна) и связывает его с `CStatusBarCtrl` объекта.

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
Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.

*dwStyle*<br/>
Задает стиль управления строкой состояния. Применить любое сочетание строки стили элемента управления, перечисленные в состояния [общие стили элемента управления](/windows/desktop/Controls/common-control-styles) в пакете Windows SDK. Этот параметр должен содержать стиль WS_CHILD. Она также должна включать WS_VISIBLE стиль.

*rect*<br/>
Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родительским для элемента управления.

*nID*<br/>
Идентификатор элемента управления дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.

##  <a name="cstatusbarctrl"></a>  CStatusBarCtrl::CStatusBarCtrl

Создает объект `CStatusBarCtrl`.

```
CStatusBarCtrl();
```

##  <a name="drawitem"></a>  CStatusBarCtrl::DrawItem

Вызывается платформой при изменении внешнего вида панели управления рисуемого владельцем состояние изменится.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) структуру, содержащую сведения о типе документа требуется.

### <a name="remarks"></a>Примечания

`itemAction` Членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CStatusBarCtrl` объекта.

Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* перед этим членом завершении функции.

##  <a name="getborders"></a>  CStatusBarCtrl::GetBorders

Извлекает элемент управления строки состояния текущей ширины горизонтальной и вертикальной границы и расстояние между прямоугольники.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>Параметры

*pBorders*<br/>
Адрес массива целых чисел, наличие трех элементов. Первый элемент принимает ширину горизонтальной границы, вторая Получает ширину вертикальной границы и третий Получает ширину границы между прямоугольниками.

*nHorz*<br/>
Ссылка на целое число, Получает ширину горизонтальной границы.

*Преобразование*<br/>
Ссылка на целое число, которое получает ширину вертикальной границы.

*nSpacing*<br/>
Ссылка на целое число, Получает ширину границы между прямоугольниками.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эти границы определить интервал между внешней границей элемента управления и прямоугольники в элементе управления, содержащие текст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

##  <a name="geticon"></a>  CStatusBarCtrl::GetIcon

Получает значок для элемента (также известный как панель) строки состояния.

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*iPart*|[in] Отсчитываемый от нуля индекс части, который содержит значок, который требуется получить. Если этот параметр имеет значение -1, строка состояния считается строка состояния простой режим.|

### <a name="return-value"></a>Возвращаемое значение

Дескриптор значка, если метод успешно; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Этот метод отправляет [SB_GETICON](/windows/desktop/Controls/sb-geticon) сообщения, который описан в пакете Windows SDK.

Элемент управления строка состояния состоит из строки панелей вывода текста, которые также называются частей. Дополнительные сведения о строке состояния, см. в разделе [реализация строки состояния в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [Установка режима объекта CStatusBarCtrl](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

### <a name="example"></a>Пример

В следующем примере кода определяет переменную, `m_statusBar`, который используется для доступа к текущей строки состояния. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>Пример

В следующем примере кода копирует значок две области строки состояния. В предыдущем разделе в примере кода мы создали элемент управления строка состояния с тремя панелями и затем добавить значок в первой области. В этом примере извлекает значок в первой области и затем добавляет его в область второй и третий.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

##  <a name="getparts"></a>  CStatusBarCtrl::GetParts

Получает количество частей строки состояния.

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>Параметры

*nParts*<br/>
Число частей, для которого требуется извлечь координаты. Если этот параметр больше, чем число частей в элементе управления, сообщение извлекает координаты только существующие элементы.

*pParts*<br/>
Адрес массива целых чисел с одинаковое количество элементов, как это число частей, определяемое *nParts*. Каждый элемент в массиве получает клиентская координата правого края, соответствующие части. Если элемент имеет значение - 1, положение правой границы для этой части расширяет возможности по правому краю строки состояния.

### <a name="return-value"></a>Возвращаемое значение

Число частей в элемент управления при успешном выполнении, или нуль, которые в противном случае.

### <a name="remarks"></a>Примечания

Эта функция-член также извлекает координата правого края на заданное число частей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

##  <a name="getrect"></a>  CStatusBarCtrl::GetRect

Возвращает ограничивающий прямоугольник части строки состояния.

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Отсчитываемый от нуля индекс части которого ограничивающий прямоугольник которой требуется извлечь.

*lpRect*<br/>
Адрес [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает ограничивающий прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

##  <a name="gettext"></a>  CStatusBarCtrl::GetText

Получение текста из указанной части элемента управления строка состояния.

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
Адрес буфера, который принимает текст. Этот параметр является строку, завершающуюся символом null.

*nPane*<br/>
Отсчитываемый от нуля индекс элемента, из которого требуется извлечь текст.

*pType*<br/>
Указатель на целое число, получает сведения о типе. Тип может быть одно из следующих значений:

- **0** текст рисуется с границей отображается ниже, чем плоскости строки состояния.

- SBT_NOBORDERS текст рисуется без границ.

- SBT_POPOUT текст рисуется с границу, чтобы иметь более высокий приоритет, чем плоскости строки состояния.

- SBT_OWNERDRAW, если текст имеет SBT_OWNERDRAW, тип, графического *pType* получает это сообщение и возвращает 32-разрядное значение, связанное с текст, а не тип длины и операции.

### <a name="return-value"></a>Возвращаемое значение

Длина в символах текста или [CString](../../atl-mfc-shared/reference/cstringt-class.md) содержащая текущий текст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

##  <a name="gettextlength"></a>  CStatusBarCtrl::GetTextLength

Получает длину в символах текста из указанной части элемента управления строка состояния.

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Отсчитываемый от нуля индекс элемента, из которого требуется извлечь текст.

*pType*<br/>
Указатель на целое число, получает сведения о типе. Тип может быть одно из следующих значений:

- **0** текст рисуется с границей отображается ниже, чем плоскости строки состояния.

- SBT_NOBORDERS текст рисуется без границ.

- SBT_OWNERDRAW текст рисуется родительским окном.

- SBT_POPOUT текст рисуется с границу, чтобы иметь более высокий приоритет, чем плоскости строки состояния.

### <a name="return-value"></a>Возвращаемое значение

Длина в символах текста.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

##  <a name="gettiptext"></a>  CStatusBarCtrl::GetTipText

Извлекает текст подсказки для панели строки состояния.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Отсчитываемый от нуля индекс панели строки состояния, чтобы получить текст подсказки.

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий текст, используемый в подсказке.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [SB_GETTIPTEXT](/windows/desktop/Controls/sb-gettiptext), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

##  <a name="issimple"></a>  CStatusBarCtrl::IsSimple

Проверяет элемент управления окна состояния, чтобы определить, является ли он в простом режиме.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления окна состояния в простом режиме; в противном случае значение равно нулю.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [SB_ISSIMPLE](/windows/desktop/Controls/sb-issimple), как описано в пакете Windows SDK.

##  <a name="setbkcolor"></a>  CStatusBarCtrl::SetBkColor

Задает цвет фона в строке состояния.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Параметры

*CR*<br/>
Значение COLORREF, которое указывает новый цвет фона. Укажите значение, CLR_DEFAULT требуется привести к строке состояния, чтобы использовать цвета фона по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Объект [COLORREF](/windows/desktop/gdi/colorref) значение, которое представляет предыдущий цвет фона по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [SB_SETBKCOLOR](/windows/desktop/Controls/sb-setbkcolor), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

##  <a name="seticon"></a>  CStatusBarCtrl::SetIcon

Задает значок для области в строке состояния.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Отсчитываемый от нуля индекс панели, который будет получать значок. Если этот параметр имеет значение -1, строка состояния считается строка простого состояния.

*hIcon*<br/>
Значок, чтобы задать дескриптор. Если это значение равно NULL, значок удаляется из части.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [SB_SETICON](/windows/desktop/Controls/sb-seticon), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CStatusBarCtrl::SetBkColor](#setbkcolor).

##  <a name="setminheight"></a>  CStatusBarCtrl::SetMinHeight

Задает минимальную высоту состояние панели области рисования элемента управления.

```
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
Минимальная высота в пикселях, элемента управления.

### <a name="remarks"></a>Примечания

Минимальная высота представляет собой сумму *Nмин.* и вдвое шире, в пикселях вертикальной границы строки состояния.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

##  <a name="setparts"></a>  CStatusBarCtrl::SetParts

Задает число частей в строке элемента управления и координата правого края каждая часть состояния.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>Параметры

*nParts*<br/>
Число частей для задания. Число частей не может быть больше 255.

*pWidths*<br/>
Адрес массива целых чисел с одинаковое количество элементов, как части, указанные в *nParts*. Каждый элемент в массиве определяет положение, в координатах клиентской области окна правой границы соответствующего части. Если элемент является - 1, положение правой границы для этой части расширяет возможности по правому краю элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

##  <a name="setsimple"></a>  CStatusBarCtrl::SetSimple

Определяет, отображает простой текст строки состояния или отображает все части элемента управления, заданные предыдущим вызовом [SetParts](#setparts).

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>Параметры

*bSimple*<br/>
[in] Флаг тип отображения. Если этот параметр имеет значение TRUE, элемент управления отображает простой текст; Если он имеет значение FALSE, выводится из нескольких частей.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 0.

### <a name="remarks"></a>Примечания

Если приложение изменяет строки состояния с непростой равным simple (или наоборот), система немедленно перерисовывает элемент управления.

##  <a name="settext"></a>  CStatusBarCtrl::SetText

Задает текст в указанной части элемента управления "Строка состояния".

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Адрес в виде оканчивающейся нулем строки, в которой указан необходимый текст. Если *nType* является SBT_OWNERDRAW, *lpszText* представляет собой 32 бита данных.

*nPane*<br/>
Отсчитываемый от нуля индекс настраиваемой части. Если это значение равно 255, строка состояния считается простым элементом управления, состоящим из одной части.

*nType*<br/>
Тип операции отрисовки. См. в разделе [сообщения SB_SETTEXT](/windows/desktop/Controls/sb-settext) список возможных значений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Сообщение объявляет недействительной часть элемента управления, который был изменен, поэтому она отображается новый текст, когда элемент управления затем получит сообщение WM_PAINT.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

##  <a name="settiptext"></a>  CStatusBarCtrl::SetTipText

Задает текст подсказки для панели строки состояния.

```
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Параметры

*nPane*<br/>
Отсчитываемый от нуля индекс панели строки состояния, чтобы получить текст подсказки.

*pszTipText*<br/>
Указатель на строку, содержащую текст подсказки.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [SB_SETTIPTEXT](/windows/desktop/Controls/sb-settiptext), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)
