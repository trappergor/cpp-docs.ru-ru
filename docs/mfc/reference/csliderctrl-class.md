---
title: Класс CSliderCtrl
ms.date: 11/04/2016
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
ms.openlocfilehash: 2e3572b34f930bb6a7d99b437c01c8aaf970e6c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751274"
---
# <a name="csliderctrl-class"></a>Класс CSliderCtrl

Предоставляет функциональные возможности стандартного элемента управления "ползунок" Windows.

## <a name="syntax"></a>Синтаксис

```
class CSliderCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Формирует объект `CSliderCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSliderCtrl::ClearSel](#clearsel)|Очищает текущий выбор в элементе управления ползунок.|
|[CSliderCtrl:ClearTics](#cleartics)|Удаляет текущие отметки тика из элемента управления ползунка.|
|[CSliderCtrl::Создание](#create)|Создает управление ползунок и `CSliderCtrl` прикрепляет его к объекту.|
|[CSliderCtrl::CreateEx](#createex)|Создает управление ползунок с указанными расширенными `CSliderCtrl` стилями Windows и прикрепляет его к объекту.|
|[CSliderCtrl::GetBuddy](#getbuddy)|Извлекает ручку в окно управления ползунок в заданном месте.|
|[CSliderCtrl:GetChannelRect](#getchannelrect)|Извлекает размер канала управления слайдером.|
|[CSliderCtrl::GetLineSize](#getlinesize)|Извлекает размер линии управления ползунок.|
|[CSliderCtrl:GetNumTics](#getnumtics)|Извлекает количество меток тикв в элементуправления ползунка.|
|[CSliderCtrl::GetPageSize](#getpagesize)|Извлекает размер страницы элемента управления ползунок.|
|[CSliderCtrl:GetPos](#getpos)|Извлекает текущее положение слайдера.|
|[CSliderCtrl:GetRange](#getrange)|Получает минимальные и максимальные позиции для ползунка.|
|[CSliderCtrl:GetRangeMax](#getrangemax)|Извлекает максимальное положение для ползунка.|
|[CSliderCtrl:GetRangeMin](#getrangemin)|Извлекает минимальное положение для ползунка.|
|[CSliderCtrl:GetSelection](#getselection)|Извлекает диапазон текущего выбора.|
|[CSliderCtrl:GetThumbLength](#getthumblength)|Извлекает длину ползунка в текущем элементе управления трекбаром.|
|[CSliderCtrl:GetThumbRect](#getthumbrect)|Извлекает размер большого пальца управления ползунок.|
|[CSliderCtrl:GetTic](#gettic)|Извлекает положение указанного тикового знака.|
|[CSliderCtrl:GetTicArray](#getticarray)|Извлекает массив позиций тиковых меток для управления ползунок.|
|[CSliderCtrl:GetTicPos](#getticpos)|Извлекает положение указанного тикового знака в координатах клиента.|
|[CSliderCtrl::GetToolTips](#gettooltips)|Извлекает ручку на элемент управления инструментария, назначенного для управления ползунок, если таковые имеется.|
|[CSliderCtrl::SetBuddy](#setbuddy)|Назначает окно в качестве окна приятеля для управления ползунок.|
|[CSliderCtrl::SetLineSize](#setlinesize)|Устанавливает размер линии управления ползунок.|
|[CSliderCtrl::SetPageSize](#setpagesize)|Устанавливает размер страницы управления ползунок.|
|[CSliderCtrl:SetPos](#setpos)|Устанавливает текущее положение слайдера.|
|[CSliderCtrl:SetRange](#setrange)|Устанавливает минимальные и максимальные позиции для ползунка.|
|[CSliderCtrl:SetRangeMax](#setrangemax)|Устанавливает максимальное положение для ползунка.|
|[CSliderCtrl:SetRangeMin](#setrangemin)|Устанавливает минимальное положение для ползунка.|
|[CSliderCtrl::SetSelection](#setselection)|Устанавливает диапазон текущего выбора.|
|[CSliderCtrl:SetThumbLength](#setthumblength)|Устанавливает длину ползунка в текущем элементе управления трекбаром.|
|[CSliderCtrl::SetTic](#settic)|Устанавливает положение указанной галочки.|
|[CSliderCtrl::SetTicFreq](#setticfreq)|Устанавливает частоту тиковых знаков на шагом управления ползунок.|
|[CSliderCtrl:SetTipSide](#settipside)|Позиции инструментарий управления, используемого трекбар управления.|
|[CSliderCtrl::SetToolTips](#settooltips)|Присваивает элемент управления набором инструментов для управления ползунок.|

## <a name="remarks"></a>Remarks

"Управление слайдер" (также известный как трекбар) представляет собой окно, содержащее ползунок и дополнительные метки. Когда пользователь перемещает ползунок, используя либо мышь, либо клавиши направления, элемент управления отправляет сообщения уведомлений для обозначения изменения.

Элементы управления слайдером полезны, если вы хотите, чтобы пользователь выбрал дискретное значение или набор последовательных значений в диапазоне. Например, можно использовать элемент управления ползунок, чтобы позволить пользователю установить скорость повторения клавиатуры, переместив ползунок на заданную отметку тик.

Этот элемент управления `CSliderCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Ползунок перемещается с шагом, которые вы указываете при его создании. Например, если указать, что ползунок должен иметь диапазон из пяти, ползунок может занимать только шесть позиций: положение на левой стороне управления ползунок и одну позицию для каждого приращения в диапазоне. Как правило, каждая из этих позиций идентифицируется по тиковой отметке.

Вы создаете ползунок с `Create` помощью `CSliderCtrl`конструктора и функции члена . После создания управления ползунок можно использовать `CSliderCtrl` функции членов, чтобы изменить многие из его свойств. Изменения, которые можно внести, включают установление минимальных и максимальных позиций для ползунка, рисование галочнок, установление диапазона выбора и изменение позиционирования ползунка.

Для получения дополнительной `CSliderCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CSliderCtrl](../../mfc/using-csliderctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="csliderctrlclearsel"></a><a name="clearsel"></a>CSliderCtrl::ClearSel

Очищает текущий выбор в элементе управления ползунок.

```cpp
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*bRedraw*<br/>
Перерисовывайте флаг. Если этот параметр является правдой, ползунок перерисовывается после очистки выделения; в противном случае ползунок не перерисовывается.

## <a name="csliderctrlcleartics"></a><a name="cleartics"></a>CSliderCtrl:ClearTics

Удаляет текущие отметки тика из элемента управления ползунка.

```cpp
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*bRedraw*<br/>
Перерисовывайте флаг. Если этот параметр является правдой, ползунок перерисовывается после очистки меток; в противном случае ползунок не перерисовывается.

## <a name="csliderctrlcreate"></a><a name="create"></a>CSliderCtrl::Создание

Создает управление ползунок и `CSliderCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления ползунок. Примените к управлению любую комбинацию [стилей управления ползунок,](/windows/win32/Controls/trackbar-control-styles)описанные в Windows SDK.

*rect*<br/>
Определяет размер и положение управления ползунок. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Определяет родительское окно управления ползунок, `CDialog`обычно . Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор управления ползунок.

### <a name="return-value"></a>Возвращаемое значение

Незерно, если инициализация была успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Вы строите `CSliderCtrl` в два этапа. Сначала позвоните в конструктор, `Create`а затем вызов , который создает управление `CSliderCtrl` ползунок и прикрепляет его к объекту.

В зависимости от значений, установленных для *dwStyle,* управление ползунок может иметь вертикальную или горизонтальную ориентацию. Он может иметь метки с обеих сторон, с обеих сторон, или ни. Он также может быть использован для определения диапазона последовательных значений.

Чтобы применить расширенные стили `Create`окон к управлению ползунок, позвоните [CreateEx](#createex) вместо .

## <a name="csliderctrlcreateex"></a><a name="createex"></a>CSliderCtrl::CreateEx

Создает элемент управления (детское окно) и `CSliderCtrl` связывает его с объектом.

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
Определяет стиль управления ползунок. Примените к управлению любую комбинацию [стилей управления ползунок,](/windows/win32/Controls/trackbar-control-styles)описанные в Windows SDK.

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

## <a name="csliderctrlcsliderctrl"></a><a name="csliderctrl"></a>CSliderCtrl::CSliderCtrl

Формирует объект `CSliderCtrl`.

```
CSliderCtrl();
```

## <a name="csliderctrlgetbuddy"></a><a name="getbuddy"></a>CSliderCtrl::GetBuddy

Извлекает ручку в окно управления ползунок в заданном месте.

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>Параметры

*fLocation*<br/>
Значение Boolean, которое указывает, какую из двух ручных оконных ручек приятеля нужно получить. Может использоваться одно из следующих значений:

- TRUE извлекает ручку к приятелю слева от ползунка. Если элемент управления ползунка использует TBS_VERT стиль, сообщение получит приятеля выше слайдера.

- FALSE извлекает ручку к приятелю справа от ползунка. Если элемент управления слайдером использует TBS_VERT стиль, сообщение получит приятеля ниже ползунка.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является окном приятеля в месте, указанном *fLocation,* или NULL, если в этом месте нет окна приятеля.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TBM_GETBUDDY,](/windows/win32/Controls/tbm-getbuddy)как описано в SDK Windows. Для описания стилей управления ползунок [см.](/windows/win32/Controls/trackbar-control-styles)

## <a name="csliderctrlgetchannelrect"></a><a name="getchannelrect"></a>CSliderCtrl:GetChannelRect

Извлекает размер и положение прямоугольника для канала управления ползунок.

```cpp
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Указатель на объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) содержащий размер и положение связующего прямоугольника канала при возвращении функции.

### <a name="remarks"></a>Remarks

Канал представляет собой область, над которой перемещается слайдер и который содержит изюминку при выборе диапазона.

## <a name="csliderctrlgetlinesize"></a><a name="getlinesize"></a>CSliderCtrl::GetLineSize

Извлекает размер линии для управления ползунок.

```
int GetLineSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер линии для управления ползунок.

### <a name="remarks"></a>Remarks

Размер строки влияет на то, сколько слайдер перемещает для TB_LINEUP и TB_LINEDOWN уведомлений. Настройка по умолчанию для размера строки составляет 1.

## <a name="csliderctrlgetnumtics"></a><a name="getnumtics"></a>CSliderCtrl:GetNumTics

Извлекает количество меток тикв в элементуправления ползунка.

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тиковых отметок в управлении ползунок.

## <a name="csliderctrlgetpagesize"></a><a name="getpagesize"></a>CSliderCtrl::GetPageSize

Извлекает размер страницы для управления слайдером.

```
int GetPageSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер страницы для управления слайдером.

### <a name="remarks"></a>Remarks

Размер страницы влияет на то, сколько слайдер перемещает для TB_PAGEUP и TB_PAGEDOWN уведомлений.

## <a name="csliderctrlgetpos"></a><a name="getpos"></a>CSliderCtrl:GetPos

Извлекает текущее положение ползунка в элемент управления ползунок.

```
int GetPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая позиция.

## <a name="csliderctrlgetrange"></a><a name="getrange"></a>CSliderCtrl:GetRange

Извлекает максимальные и минимальные позиции для ползунка в управлении ползунок.

```cpp
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
Ссылка на несколько, которая получает минимальную позицию.

*nMax*<br/>
Ссылка на несколько, которая получает максимальную позицию.

### <a name="remarks"></a>Remarks

Эта функция копирует значения в несколько, на которые ссылаются *nMin* и *nMax.*

## <a name="csliderctrlgetrangemax"></a><a name="getrangemax"></a>CSliderCtrl:GetRangeMax

Извлекает максимальное положение ползунка в управлении ползунок.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное положение элемента управления.

## <a name="csliderctrlgetrangemin"></a><a name="getrangemin"></a>CSliderCtrl:GetRangeMin

Извлекает минимальное положение для ползунка в управлении ползунок.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное положение элемента управления.

## <a name="csliderctrlgetselection"></a><a name="getselection"></a>CSliderCtrl:GetSelection

Извлекает исходные и заканчивающиеся позиции текущего выбора в элементе управления ползунок.

```cpp
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
Ссылка на несколько, которая получает исходное положение текущего выбора.

*nMax*<br/>
Ссылка на бесселит, который получает конечное положение текущего выбора.

## <a name="csliderctrlgetthumblength"></a><a name="getthumblength"></a>CSliderCtrl:GetThumbLength

Извлекает длину ползунка в текущем элементе управления трекбаром.

```
int GetThumbLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина ползунка, в пикселях.

### <a name="remarks"></a>Remarks

Этот метод отправляет [TBM_GETTHUMBLENGTH](/windows/win32/Controls/tbm-getthumblength) сообщение, которое описано в SDK Windows.

## <a name="csliderctrlgetthumbrect"></a><a name="getthumbrect"></a>CSliderCtrl:GetThumbRect

Извлекает размер и положение прямоугольника для ползунка (большого пальца) в управлении ползунок.

```cpp
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Указатель на `CRect` объект, содержащий прямоугольник для ползунка при возврате функции.

## <a name="csliderctrlgettic"></a><a name="gettic"></a>CSliderCtrl:GetTic

Извлекает положение тиковой отметки в элемент управления ползунок.

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>Параметры

*nTic*<br/>
Нулевой индекс, определяющий тик-метку.

### <a name="return-value"></a>Возвращаемое значение

Положение указанного тикового знака или - 1, если *nTic* не указывает действительный индекс.

## <a name="csliderctrlgetticarray"></a><a name="getticarray"></a>CSliderCtrl:GetTicArray

Извлекает адрес массива, содержащего позиции тиковых знаков, для управления ползунок.

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес массива, содержащий позиции тиковых отметк для управления ползунок.

## <a name="csliderctrlgetticpos"></a><a name="getticpos"></a>CSliderCtrl:GetTicPos

Извлекает текущее физическое положение тиковой отметки в элемент управления ползунок.

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>Параметры

*nTic*<br/>
Нулевой индекс, определяющий тик-метку.

### <a name="return-value"></a>Возвращаемое значение

Физическое положение в координатах клиента указанного тикового знака или - 1, если *nTic* не указывает действительный индекс.

## <a name="csliderctrlgettooltips"></a><a name="gettooltips"></a>CSliderCtrl::GetToolTips

Извлекает ручку на элемент управления инструментария, назначенного для управления ползунок, если таковые имеется.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) или NULL, если инструменты не используются. Если элемент управления ползунка не использует TBS_TOOLTIPS стиль, значение возврата null.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TBM_GETTOOLTIPS,](/windows/win32/Controls/tbm-gettooltips)как описано в SDK Windows. Обратите внимание, что `CToolTipCtrl` эта функция элемента возвращает объект вместо ручки в элемент управления.

Для описания стилей управления ползунок [см.](/windows/win32/Controls/trackbar-control-styles)

## <a name="csliderctrlsetbuddy"></a><a name="setbuddy"></a>CSliderCtrl::SetBuddy

Назначает окно в качестве окна приятеля для управления ползунок.

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>Параметры

*pWndBuddy*<br/>
Указатель на `CWnd` объект, который будет установлен в качестве приятеля управления ползунок.

*fLocation*<br/>
Значение, определяющее место, на котором отображается окно приятеля. Значение может быть одним из следующих.

- ПРАВДА приятель появится слева от трекбара, если контроль трекбара использует TBS_HORZ стиль. Если трекбар использует TBS_VERT стиль, приятель появляется над управлением трекбара.

- FALSE Приятель будет отображаться справа от трекбара, если контроль трекбара использует TBS_HORZ стиль. Если трекбар использует TBS_VERT стиль, приятель отображается ниже элемента управления трекбаром.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который ранее был назначен управлению ползунок в этом месте.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TBM_SETBUDDY,](/windows/win32/Controls/tbm-setbuddy)как описано в SDK Windows. Обратите внимание, что эта `CWnd` функция члена использует указатели на объекты, а не оконные ручки как для значения возврата, так и для параметра.

Для описания стилей управления ползунок [см.](/windows/win32/Controls/trackbar-control-styles)

## <a name="csliderctrlsetlinesize"></a><a name="setlinesize"></a>CSliderCtrl::SetLineSize

Устанавливает размер линии для управления ползунок.

```
int SetLineSize(int nSize);
```

### <a name="parameters"></a>Параметры

*Nsize*<br/>
Новый размер линии управления ползунок.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий размер строки.

### <a name="remarks"></a>Remarks

Размер строки влияет на то, сколько слайдер перемещает для TB_LINEUP и TB_LINEDOWN уведомлений.

## <a name="csliderctrlsetpagesize"></a><a name="setpagesize"></a>CSliderCtrl::SetPageSize

Устанавливает размер страницы для управления ползунок.

```
int SetPageSize(int nSize);
```

### <a name="parameters"></a>Параметры

*Nsize*<br/>
Новый размер страницы управления ползунок.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий размер страницы.

### <a name="remarks"></a>Remarks

Размер страницы влияет на то, сколько слайдер перемещает для TB_PAGEUP и TB_PAGEDOWN уведомлений.

## <a name="csliderctrlsetpos"></a><a name="setpos"></a>CSliderCtrl:SetPos

Устанавливает текущее положение ползунка в управлении ползунок.

```cpp
void SetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Определяет новое положение слайдера.

## <a name="csliderctrlsetrange"></a><a name="setrange"></a>CSliderCtrl:SetRange

Устанавливает диапазон (минимальные и максимальные позиции) для ползунка в управлении ползунок.

```cpp
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
Минимальное положение для ползунка.

*nMax*<br/>
Максимальное положение для ползунка.

*bRedraw*<br/>
Перерисовка флага. Если этот параметр является правдой, ползунок перерисовывается после набора диапазона; в противном случае ползунок не перерисовывается.

## <a name="csliderctrlsetrangemax"></a><a name="setrangemax"></a>CSliderCtrl:SetRangeMax

Устанавливает максимальный диапазон для ползунка в управлении ползунок.

```cpp
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*nMax*<br/>
Максимальное положение для ползунка.

*bRedraw*<br/>
Перерисовка флага. Если этот параметр является правдой, ползунок перерисовывается после набора диапазона; в противном случае ползунок не перерисовывается.

## <a name="csliderctrlsetrangemin"></a><a name="setrangemin"></a>CSliderCtrl:SetRangeMin

Устанавливает минимальный диапазон для ползунка в управлении ползунок.

```cpp
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
Минимальное положение для ползунка.

*bRedraw*<br/>
Перерисовка флага. Если этот параметр является правдой, ползунок перерисовывается после набора диапазона; в противном случае ползунок не перерисовывается.

## <a name="csliderctrlsetselection"></a><a name="setselection"></a>CSliderCtrl::SetSelection

Устанавливает начальные и заканчивающиеся позиции для текущего выбора в элементе управления ползунок.

```cpp
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
Исходное положение для слайдера.

*nMax*<br/>
Окончание положения для слайдера.

## <a name="csliderctrlsetthumblength"></a><a name="setthumblength"></a>CSliderCtrl:SetThumbLength

Устанавливает длину ползунка в текущем элементе управления трекбаром.

```cpp
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*nДлина*|(в) Длина ползунка, в пикселях.|

### <a name="remarks"></a>Remarks

Этот метод требует, чтобы контроль трекбара был установлен [в TBS_FIXEDLENGTH](/windows/win32/Controls/trackbar-control-styles) стиле.

Этот метод отправляет [TBM_SETTHUMBLENGTH](/windows/win32/Controls/tbm-setthumblength) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_sliderCtrl`переменную, которая используется для доступа к текущему элементу управления трекбаром. Пример также определяет переменную, `thumbLength`которая используется для хранения длины большого пальца по умолчанию компонента управления трекбаром. Эти переменные используются в следующем примере.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает компонент большого пальца управления трекбаром в два раза его длина по умолчанию.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

## <a name="csliderctrlsettic"></a><a name="settic"></a>CSliderCtrl::SetTic

Устанавливает положение тиковой отметки в управлении ползунок.

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>Параметры

*nTic*<br/>
Положение тикового знака. Этот параметр должен указывать положительное значение.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метка галочки установлена; в противном случае 0.

## <a name="csliderctrlsetticfreq"></a><a name="setticfreq"></a>CSliderCtrl::SetTicFreq

Устанавливает частоту, с которой тиковые метки отображаются в ползунок.

```cpp
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>Параметры

*nFreq*<br/>
Частота знаков тика.

### <a name="remarks"></a>Remarks

Например, если частота установлена до 2, для каждого другого приращения в диапазоне слайдера отображается тиковая отметка. Настройка по умолчанию для частоты составляет 1 (т.е. каждый приращение в диапазоне связан о галочку).

Для использования этой функции необходимо создать элемент управления со стилем TBS_AUTOTICKS. Для получения дополнительной информации [см. CSliderCtrl::Создать](#create).

## <a name="csliderctrlsettipside"></a><a name="settipside"></a>CSliderCtrl:SetTipSide

Позиции инструментарий управления, используемого трекбар управления.

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>Параметры

*nLocation*<br/>
Значение, представляющее место, на котором отображается элемент управления набором инструментов. Список возможных значений можно узнать в сообщении Win32 [TBM_SETTIPSIDE,](/windows/win32/Controls/tbm-settipside)как описано в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Значение, представляющее предыдущее местоположение элемента управления набором инструментов. Значение возврата равно одному из возможных значений для *nLocation.*

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 TBM_SETTIPSIDE, как описано в SDK Windows. Slider управляет, которые используют инструменты отображения TBS_TOOLTIPS стиле. Для описания стилей управления ползунок [см.](/windows/win32/Controls/trackbar-control-styles)

## <a name="csliderctrlsettooltips"></a><a name="settooltips"></a>CSliderCtrl::SetToolTips

Присваивает элемент управления набором инструментов для управления ползунок.

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Параметры

*pWndTip*<br/>
Указатель на объект [CToolTipCtrl,](../../mfc/reference/ctooltipctrl-class.md) содержащий инструменты для использования с управлением слайдером.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [TBM_SETTOOLTIPS,](/windows/win32/Controls/tbm-settooltips)как описано в SDK Windows. Когда элемент управления ползунок создается с TBS_TOOLTIPS стилем, он создает элемент управления инструментарием по умолчанию, который отображается рядом с слайдером, отображая текущее положение слайдера. Для описания стилей управления ползунок [см.](/windows/win32/Controls/trackbar-control-styles)

## <a name="see-also"></a>См. также раздел

[MFC Образец CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CProgressCtrl](../../mfc/reference/cprogressctrl-class.md)
