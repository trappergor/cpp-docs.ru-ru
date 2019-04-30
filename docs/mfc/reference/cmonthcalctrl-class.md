---
title: Cmonthcalctrl-класс
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: bd062a4e0d4db364c9cb628608c6af165dc0edc2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338027"
---
# <a name="cmonthcalctrl-class"></a>Cmonthcalctrl-класс

Инкапсулирует функциональность элемента управления "календарь месяца".

## <a name="syntax"></a>Синтаксис

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Создает объект `CMonthCalCtrl`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMonthCalCtrl::Create](#create)|Создает элемент управления calendar month и присоединяет его к `CMonthCalCtrl` объекта.|
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Получает ширину границы элемента управления calendar текущего месяца.|
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|Возвращает число календарей, отображаемый в элементе управления calendar текущего месяца.|
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Извлекает сведения об элементе управления календаря текущего месяца.|
|[CMonthCalCtrl::GetCalID](#getcalid)|Извлекает идентификатор календаря для элемента управления calendar текущего месяца.|
|[CMonthCalCtrl::GetColor](#getcolor)|Получает цвет в указанную область элемента управления календаря на месяц.|
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|Извлекает представления, отображаемого элементом управления calendar текущего месяца.|
|[CMonthCalCtrl::GetCurSel](#getcursel)|Получает системное время, как указано в выбранной даты.|
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Возвращает первый день недели, отображаемый в самом левом столбце календаря.|
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Извлекает текущее максимальное число дней, которые могут быть выбраны в элементе управления calendar month.|
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|Получает максимальную ширину строки «Сегодня» для элемента управления calendar текущего месяца.|
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Получает минимальный размер, необходимый для отображения полного месяца в элементе управления calendar month.|
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Получает скорость прокрутки для элемента управления календаря на месяц.|
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|Извлекает даты сведения, представляющий высоких и низких ограничений отображение элемента управления Календарь месяца.|
|[CMonthCalCtrl::GetRange](#getrange)|Извлекает текущие даты минимальное и максимальное значение в элементе управления calendar month.|
|[CMonthCalCtrl::GetSelRange](#getselrange)|Возвращает сведения о датах, представляющий верхний и нижний пределы диапазона дат, выбранного пользователем.|
|[CMonthCalCtrl::GetToday](#gettoday)|Возвращает сведения о датах по дате, указанной как «сегодня» для элемента управления календаря на месяц.|
|[CMonthCalCtrl::HitTest](#hittest)|Определяет, какие части управления Календарь месяца в определенный момент на экране.|
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление века.|
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление десять лет.|
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление месяца.|
|[CMonthCalCtrl::IsYearView](#isyearview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление года.|
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Задает ширину границы элемента управления calendar текущего месяца.|
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Задает ширину границы элемента управления calendar текущего месяца, по умолчанию.|
|[CMonthCalCtrl::SetCalID](#setcalid)|Задает идентификатор календаря для элемента управления calendar текущего месяца.|
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|Задает элемент управления calendar текущего месяца для отображения представления века.|
|[CMonthCalCtrl::SetColor](#setcolor)|Задает цвет в указанную область элемента управления календаря на месяц.|
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|Задает элемент управления calendar текущего месяца для отображения в указанном представлении.|
|[CMonthCalCtrl::SetCurSel](#setcursel)|Задает выбранную дату для элемента управления календаря на месяц.|
|[CMonthCalCtrl::SetDayState](#setdaystate)|Задает отображение дней в месяц календаря.|
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|Наборы текущий месяц календаря управление представление десять лет.|
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Задает день недели, отображаемый в самом левом столбце календаря.|
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|Задает максимальное число дней, которые могут быть выбраны в элементе управления calendar month.|
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Задает скорость прокрутки для элемента управления календаря на месяц.|
|[CMonthCalCtrl::SetMonthView](#setmonthview)|Задает элемент управления calendar текущего месяца для отображения представления месяца.|
|[CMonthCalCtrl::SetRange](#setrange)|Задает минимальное и максимальное допустимые даты для элемента управления календаря на месяц.|
|[CMonthCalCtrl::SetSelRange](#setselrange)|Задает выделение календарь на месяц управление указанного диапазона дат.|
|[CMonthCalCtrl::SetToday](#settoday)|Задает элемент управления calendar за текущий день.|
|[CMonthCalCtrl::SetYearView](#setyearview)|Задает текущий месяц календаря управление представление года.|
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|Перерисовывает месячный календарь контролировать размер минимум, один месяц.|
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Для элемента управления calendar текущего месяца вычисляет наименьший прямоугольник, содержащий все календари, которые помещаются в заданном прямоугольнике.|

## <a name="remarks"></a>Примечания

Элемент управления calendar month предоставляет пользователю интерфейс простой календаря, из которого пользователь может выбрать дату. Пользователь может изменить отображение по:

- Переход назад и вперед, от месяца к месяцу.

- Если щелкнуть сегодня текст, отображаемый в текущий день, (если не используется стиль MCS_NOTODAY).

- Комплектации, месяц или год из всплывающего меню.

Вы можете настроить месяца календаря элемента управления, применяя различные стили к объекту, при ее создании. Эти стили описаны в [стили элемента управления Calendar Month](/windows/desktop/Controls/month-calendar-control-styles) в пакете Windows SDK.

Элемент управления Календарь месяца можно отображать более чем одного месяца, и он может указать специальное дней (такие как праздники) путем выделения жирным шрифтом дату.

Дополнительные сведения об использовании элемента управления calendar month см. в разделе [использование CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxdtctl.h

##  <a name="cmonthcalctrl"></a>  CMonthCalCtrl::CMonthCalCtrl

Создает объект `CMonthCalCtrl`.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Примечания

Необходимо вызвать `Create` после создания объекта.

##  <a name="create"></a>  CMonthCalCtrl::Create

Создает элемент управления calendar month и присоединяет его к `CMonthCalCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает сочетание Windows стили, примененный к элементу управления Календарь месяца. См. в разделе [стили элемента управления Calendar Month](/windows/desktop/Controls/month-calendar-control-styles) в пакете SDK для Windows, Дополнительные сведения о стилях.

*rect*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структуры. Содержит положение и размер элемента управления calendar month.

*pt*<br/>
Ссылку на [ТОЧКИ](/previous-versions/dd162805\(v=vs.85\)) структуру, которая определяет расположение элемента управления calendar month.

*pParentWnd*<br/>
Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся родительского окна элемента управления calendar month. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления calendar month элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Создание месяц календаря элемента управления в два этапа:

1. Вызовите [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) для создания `CMonthCalCtrl` объекта.

1. Вызов этой функцией-членом, которая создает элемент управления calendar month и присоединяет его к `CMonthCalCtrl` объекта.

При вызове `Create`, общие элементы управления инициализируются. Версия `Create` вы вызова определяет способ изменения размеров:

- Чтобы MFC автоматически размеры элемента управления до одного месяца, вызовите переопределения, которое использует *pt* параметра.

- Чтобы самостоятельно размеры элемента управления, вызовите переопределение метода этой функции, которая использует *rect* параметра.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

##  <a name="getcalendarborder"></a>  CMonthCalCtrl::GetCalendarBorder

Получает ширину границы элемента управления calendar текущего месяца.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина границы элемента управления, в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCALENDARBORDER](/windows/desktop/Controls/mcm-getcalendarborder) сообщения, который описан в пакете Windows SDK.

##  <a name="getcalendarcount"></a>  CMonthCalCtrl::GetCalendarCount

Возвращает число календарей, отображаемый в элементе управления calendar текущего месяца.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число календарей, отображаемой в элементе управления calendar month. Максимальное число календарей равна 12.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCALENDARCOUNT](/windows/desktop/Controls/mcm-getcalendarcount) сообщения, который описан в пакете Windows SDK.

##  <a name="getcalendargridinfo"></a>  CMonthCalCtrl::GetCalendarGridInfo

Извлекает сведения об элементе управления календаря текущего месяца.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pmcGridInfo*|[out] Указатель на [MCGRIDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagmcgridinfo) структуры, получающий сведения об элементе управления календаря текущего месяца. Вызывающий объект отвечает за выделение и инициализации этой структуры.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCALENDARGRIDINFO](/windows/desktop/Controls/mcm-getcalendargridinfo) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода используется `GetCalendarGridInfo` метод для извлечения календарная дата, который отображает элемент управления calendar текущего месяца.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

##  <a name="getcalid"></a>  CMonthCalCtrl::GetCalID

Извлекает идентификатор календаря для элемента управления calendar текущего месяца.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Один из [идентификатор календаря](/windows/desktop/Intl/calendar-identifiers) константы.

### <a name="remarks"></a>Примечания

Идентификатор календаря обозначает календаре конкретного региона, например григорианский (локализованный), японский или хиджра календари. Приложение может использовать идентификатор календаря, который имеет поддержка функции различных языков.

Этот метод отправляет [MCM_GETCALID](/windows/desktop/Controls/mcm-getcalid) сообщения, который описан в пакете Windows SDK.

##  <a name="getcolor"></a>  CMonthCalCtrl::GetColor

Получает цвет в той части месяца календарь на элемент управления, заданный *nRegion*.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Параметры

*nRegion*<br/>
Область элемента управления calendar month, из которого извлекается цвет. Список значений, см. в разделе *nRegion* параметр [SetColor](#setcolor).

### <a name="return-value"></a>Возвращаемое значение

Объект [COLORREF](/windows/desktop/gdi/colorref) значение, указывающее цвет, связанный с частью элемента управления calendar month, при успешном выполнении. В противном случае эта функция-член возвращает значение -1.

##  <a name="getcurrentview"></a>  CMonthCalCtrl::GetCurrentView

Извлекает представления, отображаемого элементом управления calendar текущего месяца.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее представление, которое указывается одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|MCMV_MONTH|Представление за месяц.|
|MCMV_YEAR|Ежегодное представление|
|MCMV_DECADE|Представление десять лет|
|MCMV_CENTURY|Представление веке|

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

Следующие отчеты пример кода, просмотра месячный календарь которых отображается элемент управления в данный момент.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

##  <a name="getcursel"></a>  CMonthCalCtrl::GetCurSel

Получает системное время, как указано в выбранной даты.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта. Получает текущее время.

*pDateTime*<br/>
Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуры, который будет получать сведения о дате, выбранных в настоящий момент. Этот параметр должен быть допустимым адресом и не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; otherwize 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETCURSEL](/windows/desktop/Controls/mcm-getcursel), как описано в пакете Windows SDK.

> [!NOTE]
>  Эта функция-член не выполняется, если стиль имеет значение MCS_MULTISELECT.

В реализации MFC `GetCurSel`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

##  <a name="getfirstdayofweek"></a>  CMonthCalCtrl::GetFirstDayOfWeek

Возвращает первый день недели, отображаемый в самом левом столбце календаря.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Параметры

*pbLocal*<br/>
Указатель на Логическое значение. Если значение равно нулю, значение элемента управления не соответствует параметру в панели управления.

### <a name="return-value"></a>Возвращаемое значение

Целое число, представляющее первый день недели. См. в разделе **"Примечания"** Дополнительные сведения о представляют эти целых чисел.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-getfirstdayofweek), как описано в пакете Windows SDK. Дни недели представлены как целые числа, следующим образом.

|Значение|День недели|
|-----------|---------------------|
|0|понедельник|
|1|Вторник|
|2|среда|
|3|Четверг|
|4|пятница|
|5|Суббота|
|6|Воскресенье|

### <a name="example"></a>Пример

  См. в примере [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek).

##  <a name="getmaxselcount"></a>  CMonthCalCtrl::GetMaxSelCount

Извлекает текущее максимальное число дней, которые могут быть выбраны в элементе управления calendar month.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целое число, представляющее общее число дней, которые могут быть выбраны для элемента управления.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETMAXSELCOUNT](/windows/desktop/Controls/mcm-getmaxselcount), как описано в пакете Windows SDK. Используйте эту функцию-член для элементов управления с MCS_MULTISELECT набор стилей.

### <a name="example"></a>Пример

  См. в примере [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount).

##  <a name="getmaxtodaywidth"></a>  CMonthCalCtrl::GetMaxTodayWidth

Получает максимальную ширину строки «Сегодня» для элемента управления calendar текущего месяца.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина «Сегодня» строки в пикселях.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода показано `GetMaxTodayWidth` метод.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Примечания

Пользователь может возвращать текущую дату, щелкнув строку «Сегодня», которая отображается в нижней части элемента управления Календарь месяца. Строка «Сегодня» содержит текст метки и даты.

Этот метод отправляет [MCM_GETMAXTODAYWIDTH](/windows/desktop/Controls/mcm-getmaxtodaywidth) сообщения, который описан в пакете Windows SDK.

##  <a name="getminreqrect"></a>  CMonthCalCtrl::GetMinReqRect

Получает минимальный размер, необходимый для отображения полного месяца в элементе управления calendar month.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Параметры

*pRect*<br/>
Указатель на [RECT](/previous-versions/dd162897\(v=vs.85\)) структуру, которая будет получать сведения ограничивающий прямоугольник. Этот параметр должен быть допустимым адресом и не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

При успешном завершении, эта функция-член возвращает ненулевое значение и `lpRect` Получает ограничивающий данные. Если операция завершилась неудачей, функция-член возвращает значение 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETMINREQRECT](/windows/desktop/Controls/mcm-getminreqrect), как описано в пакете Windows SDK.

##  <a name="getmonthdelta"></a>  CMonthCalCtrl::GetMonthDelta

Получает скорость прокрутки для элемента управления календаря на месяц.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Возвращаемое значение

Скорость прокрутки для элемента управления calendar month. Скорость прокрутки — количество месяцев, что элемент управления перемещается отображения, когда пользователь нажимает кнопку прокрутки один раз.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETMONTHDELTA](/windows/desktop/Controls/mcm-getmonthdelta), как описано в пакете Windows SDK.

##  <a name="getmonthrange"></a>  CMonthCalCtrl::GetMonthRange

Извлекает даты сведения, представляющий высоких и низких ограничений отображение элемента управления Календарь месяца.

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>Параметры

*refMinRange*<br/>
Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий минимальное даты, допустимое.

*refMaxRange*<br/>
Ссылку на `COleDateTime` или `CTime` объект, содержащий Максимальная допустимая дата.

*pMinRange*<br/>
Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую даты в наименьшее конец диапазона.

*pMaxRange*<br/>
Указатель на `SYSTEMTIME` структуру, содержащую дату, указанную в наибольшее конец диапазона.

*dwFlags*<br/>
Значение, указывающее область границы диапазона, который требуется получить. Это значение должно быть одно из следующих значений.

|Значение|Значение|
|-----------|-------------|
|GMR_DAYSTATE|Включить начальные и завершающие месяцы видимого диапазона, в которых отображаются только частично.|
|GMR_VISIBLE|Включать только те месяцы, которые отображаются полностью.|

### <a name="return-value"></a>Возвращаемое значение

Указывает целое число, представляющий диапазон, в течение месяцев, занимаемых двумя ограничениями *refMinRange* и *refMaxRange* в первая и вторая версии или *pMinRange* и *pMaxRange* в третьей версии.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETMONTHRANGE](/windows/desktop/Controls/mcm-getmonthrange), как описано в пакете Windows SDK. В реализации MFC `GetMonthRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

### <a name="example"></a>Пример

  См. в примере [CMonthCalCtrl::SetDayState](#setdaystate).

##  <a name="getrange"></a>  CMonthCalCtrl::GetRange

Извлекает текущие даты минимальное и максимальное значение в элементе управления calendar month.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Параметры

*pMinRange*<br/>
Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую даты в наименьшее конец диапазона.

*pMaxRange*<br/>
Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую дату, указанную в наибольшее конец диапазона.

### <a name="return-value"></a>Возвращаемое значение

DWORD, которое может быть равно нулю (устанавливаются без ограничений) или сочетания из следующих значений, которые указывают сведения об ограничении.

|Значение|Значение|
|-----------|-------------|
|GDTR_MAX|Максимальное ограничение установлено для элемента управления; *pMaxRange* является допустимым и содержит сведения о применимых дате.|
|GDTR_MIN|Минимальное ограничение установлено для элемента управления; *pMinRange* является допустимым и содержит сведения о применимых дате.|

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETRANGE](/windows/desktop/Controls/mcm-getrange), как описано в пакете Windows SDK. В реализации MFC `GetRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

##  <a name="getselrange"></a>  CMonthCalCtrl::GetSelRange

Возвращает сведения о датах, представляющий верхний и нижний пределы диапазона дат, выбранного пользователем.

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Параметры

*refMinRange*<br/>
Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий минимальное даты, допустимое.

*refMaxRange*<br/>
Ссылку на `COleDateTime` или `CTime` объект, содержащий Максимальная допустимая дата.

*pMinRange*<br/>
Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую даты в наименьшее конец диапазона.

*pMaxRange*<br/>
Указатель на `SYSTEMTIME` структуру, содержащую дату, указанную в наибольшее конец диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETSELRANGE](/windows/desktop/Controls/mcm-getselrange), как описано в пакете Windows SDK. `GetSelRange` Если применить к элементу управления Календарь месяца, использует ли стиль MCS_MULTISELECT завершится ошибкой.

В реализации MFC `GetSelRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

##  <a name="gettoday"></a>  CMonthCalCtrl::GetToday

Возвращает сведения о датах по дате, указанной как «сегодня» для элемента управления календаря на месяц.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , указывающий текущий день.

*pDateTime*<br/>
Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуры, который будет получать сведения о дате. Этот параметр должен быть допустимым адресом и не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_GETTODAY](/windows/desktop/Controls/mcm-gettoday), как описано в пакете Windows SDK. В реализации MFC `GetToday`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

##  <a name="hittest"></a>  CMonthCalCtrl::HitTest

Определяет какие управления Календарь месяца, если он имеется в указанной позиции.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Параметры

*pMCHitTest*<br/>
Указатель на [MCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-mchittestinfo) указывает структуру, содержащую проверку попадания для элемента управления calendar month.

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD. Равным **uHit** членом `MCHITTESTINFO` структуры.

### <a name="remarks"></a>Примечания

`HitTest` использует `MCHITTESTINFO` структуру, которая содержит сведения о проверке нажатия.

##  <a name="iscenturyview"></a>  CMonthCalCtrl::IsCenturyView

Указывает, является ли текущее представление элемента управления calendar текущего месяца представление века.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущим представлением является представления века. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) сообщения, который описан в пакете Windows SDK. Если это сообщение возвращается MCMV_CENTURY, этот метод возвращает значение TRUE.

##  <a name="isdecadeview"></a>  CMonthCalCtrl::IsDecadeView

Указывает, является ли текущее представление элемента управления calendar текущего месяца представление десять лет.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущим представлением является представление десять лет; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) сообщения, который описан в пакете Windows SDK. Если это сообщение возвращается MCMV_DECADE, этот метод возвращает значение TRUE.

##  <a name="ismonthview"></a>  CMonthCalCtrl::IsMonthView

Указывает, является ли текущее представление элемента управления calendar текущего месяца представление месяца.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущим представлением является месяц; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) сообщения, который описан в пакете Windows SDK. Если это сообщение возвращается MCMV_MONTH, этот метод возвращает значение TRUE.

##  <a name="isyearview"></a>  CMonthCalCtrl::IsYearView

Указывает, является ли текущее представление элемента управления calendar текущего месяца представление года.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущим представлением является представление года; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) сообщения, который описан в пакете Windows SDK. Если это сообщение возвращается MCMV_YEAR, этот метод возвращает значение TRUE.

##  <a name="setcalendarborder"></a>  CMonthCalCtrl::SetCalendarBorder

Задает ширину границы элемента управления calendar текущего месяца.

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*cxyBorder*|[in] Ширина границы в пикселях.|

### <a name="remarks"></a>Примечания

Если этот метод выполняется успешно, ширину границы присваивается *cxyBorder* параметра. В противном случае ширину границы сбрасывается в значение по умолчанию, заданный текущим [темы](/windows/desktop/Controls/visual-styles-overview), или нуль, если темы не используются.

Этот метод отправляет [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода устанавливается ширина границы месячный календарь управления до восьми пикселей. Используйте [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) метод, чтобы определить, является ли этот метод выполнен успешно.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

##  <a name="setcalendarborderdefault"></a>  CMonthCalCtrl::SetCalendarBorderDefault

Задает ширину границы элемента управления calendar текущего месяца, по умолчанию.

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Примечания

Ширина границы присвоено значение по умолчанию, заданный текущим [темы](/windows/desktop/Controls/visual-styles-overview), или нуль, если темы не используются.

Этот метод отправляет [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) сообщения, который описан в пакете Windows SDK.

##  <a name="setcalid"></a>  CMonthCalCtrl::SetCalID

Задает идентификатор календаря для элемента управления calendar текущего месяца.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*CALID*|[in] Один из [идентификатор календаря](/windows/desktop/Intl/calendar-identifiers) константы.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Идентификатор календаря указывает календаре конкретного региона, например григорианский (локализованный), японский или хиджра календари. Используйте `SetCalID` метод для отображения календаря, который задается параметром *calid* параметра, если на вашем компьютере установлен данный языковой стандарт, с календарем.

Этот метод отправляет [MCM_SETCALID](/windows/desktop/Controls/mcm-setcalid) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода задает элемент управления Календарь месяца для отображения календаря японских императоров. `SetCalID` Метод завершается успешно только в том случае, если этот календарь установлен на компьютере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

##  <a name="setcenturyview"></a>  CMonthCalCtrl::SetCenturyView

Задает элемент управления calendar текущего месяца для отображения представления века.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, чтобы задать представление `MCMV_CENTURY`, который представляет представление века.

##  <a name="setcolor"></a>  CMonthCalCtrl::SetColor

Задает цвет в указанную область элемента управления календаря на месяц.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Параметры

*nRegion*<br/>
Целочисленное значение, задающее цвет календаря какой месяц для задания. Это значение может быть одно из следующих значений.

|Значение|Значение|
|-----------|-------------|
|MCSC_BACKGROUND|Цвет фона между месяцами.|
|MCSC_MONTHBK|Цвет фона в течение месяца.|
|MCSC_TEXT|Цвет, используемый для отображения текста в течение месяца.|
|MCSC_TITLEBK|Цвет фона, отображаемое в заголовке календаря.|
|MCSC_TITLETEXT|Цвет, используемый для отображения текста в пределах заголовка календаря.|
|MCSC_TRAILINGTEXT|Цвет, используемый для отображения текста заголовка и в конце дня. Заголовок и начальные дни — дни месяца предыдущие и следующие, которые отображаются на текущем календаре.|

*ref*<br/>
Значение COLORREF нового параметра цвет указанную часть элемента управления calendar month.

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющий предыдущее значение цвета указанную часть элемента управления Календарь месяца, в случае успеха. В противном случае оно возвращает -1.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETCOLOR](/windows/desktop/Controls/mcm-setcolor), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

##  <a name="setcurrentview"></a>  CMonthCalCtrl::SetCurrentView

Задает элемент управления calendar текущего месяца для отображения в указанном представлении.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwNewView*|[in] Одно из следующих значений, указывающих ежемесячно, ежегодно, десять лет или представления века.<br /><br /> MCMV_MONTH: Представление за месяц.<br /><br /> MCMV_YEAR: Ежегодное представление<br /><br /> MCMV_DECADE: Представление десять лет<br /><br /> MCMV_CENTURY: Представление веке|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_SETCURRENTVIEW](/windows/desktop/Controls/mcm-setcurrentview) сообщения, который описан в пакете Windows SDK.

##  <a name="setcursel"></a>  CMonthCalCtrl::SetCurSel

Задает выбранную дату для элемента управления календаря на месяц.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , указывающий элемент управления calendar month, выбранных в настоящий момент.

*pDateTime*<br/>
Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую дату в качестве текущего выделения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETCURSEL](/windows/desktop/Controls/mcm-setcursel), как описано в пакете Windows SDK. В реализации MFC `SetCurSel`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

##  <a name="setdaystate"></a>  CMonthCalCtrl::SetDayState

Задает отображение дней в месяц календаря.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Параметры

*nMonths*<br/>
Значение, указывающее, какое количество элементов в массиве, *pStates* указывает.

*pStates*<br/>
Указатель на [MONTHDAYSTATE](/windows/desktop/Controls/monthdaystate) массив значений, которые определяют, как нарисовать элемент управления calendar month каждый день в его отображение. Тип данных MONTHDAYSTATE представляет собой битовое поле, где каждый бит (от 1 до 31) представляет состояние в день в месяц. Если бит равен в, соответствующий день будет отображаться полужирным шрифтом; в противном случае он будет отображаться с отсутствие курсива.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETDAYSTATE](/windows/desktop/Controls/mcm-setdaystate), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

##  <a name="setdecadeview"></a>  CMonthCalCtrl::SetDecadeView

Наборы текущий месяц календаря управление представление десять лет.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, чтобы задать представление `MCMV_DECADE`, который представляет представление десять лет.

##  <a name="setfirstdayofweek"></a>  CMonthCalCtrl::SetFirstDayOfWeek

Задает день недели, отображаемый в самом левом столбце календаря.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Параметры

*iDay*<br/>
Целое число, представляющее день — задать в качестве первого дня недели. Это значение должно быть одним из номеров день. См. в разделе [GetFirstDayOfWeek](#getfirstdayofweek) описание номера дня.

*lpnOld*<br/>
Указатель на целое число, представляющее первый день недели, ранее набора.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если предыдущий первый день недели присвоено значение, отличным от типа LOCALE_IFIRSTDAYOFWEEK, это день, в параметр панели управления. В противном случае эта функция возвращает 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-setfirstdayofweek), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

##  <a name="setmaxselcount"></a>  CMonthCalCtrl::SetMaxSelCount

Задает максимальное число дней, которые могут быть выбраны в элементе управления calendar month.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Параметры

*Nмакс.*<br/>
Значение, которое будет задано для представления максимальное число дней, доступный для выбора.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETMAXSELCOUNT](/windows/desktop/Controls/mcm-setmaxselcount), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

##  <a name="setmonthdelta"></a>  CMonthCalCtrl::SetMonthDelta

Задает скорость прокрутки для элемента управления календаря на месяц.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Параметры

*класса iDelta*<br/>
Число месяцев в качестве скорость прокрутки элемента управления. Если это значение равно нулю, изменение количества месяцев сбрасывается до значения по умолчанию — количество месяцев, отображаемых в элементе управления.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий скорость прокрутки. Если скорость прокрутки не было задано ранее, возвращаемое значение равно 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETMONTHDELTA](/windows/desktop/Controls/mcm-setmonthdelta), как описано в пакете Windows SDK.

##  <a name="setmonthview"></a>  CMonthCalCtrl::SetMonthView

Задает элемент управления calendar текущего месяца для отображения представления месяца.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, позволяющий настраивать представление для MCMV_MONTH, который представляет представление месяца.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода задает элемент управления Календарь месяца для отображения месяца, года, десять лет и представления века.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

##  <a name="setrange"></a>  CMonthCalCtrl::SetRange

Задает минимальное и максимальное допустимые даты для элемента управления календаря на месяц.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Параметры

*pMinRange*<br/>
Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую даты в наименьшее конец диапазона.

*pMaxRange*<br/>
Указатель на `COleDateTime` объекта, `CTime` объекта, или `SYSTEMTIME` структуру, содержащую дату, указанную в наибольшее конец диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETRANGE](/windows/desktop/Controls/mcm-setrange), как описано в пакете Windows SDK. В реализации MFC `SetRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

### <a name="example"></a>Пример

  См. в примере [CMonthCalCtrl::GetRange](#getrange).

##  <a name="setselrange"></a>  CMonthCalCtrl::SetSelRange

Задает выделение календарь на месяц управление указанного диапазона дат.

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Параметры

*pMinRange*<br/>
Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую даты в наименьшее конец диапазона.

*pMaxRange*<br/>
Указатель на `COleDateTime` объекта, `CTime` объекта, или `SYSTEMTIME` структуру, содержащую дату, указанную в наибольшее конец диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETSELRANGE](/windows/desktop/Controls/mcm-setselrange), как описано в пакете Windows SDK. В реализации MFC `SetSelRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.

##  <a name="settoday"></a>  CMonthCalCtrl::SetToday

Задает элемент управления calendar за текущий день.

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
  void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий текущую дату.

*pDateTime*<br/>
Во второй версии, указатель на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий сведения о текущей дате. В третьей версии, указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую сведения о текущей дате.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [MCM_SETTODAY](/windows/desktop/Controls/mcm-settoday), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CMonthCalCtrl::GetToday](#gettoday).

##  <a name="setyearview"></a>  CMonthCalCtrl::SetYearView

Задает текущий месяц календаря управление представление года.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, позволяющий настраивать представление для MCMV_YEAR, который представляет ежегодное представление.

##  <a name="sizeminreq"></a>  CMonthCalCtrl::SizeMinReq

Отображает месяц календаря до минимума, размер, который отображает один месяц.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Параметры

*bRepaint*<br/>
Указывает, является ли элемент управления окрашивание. По умолчанию TRUE. Если значение равно FALSE, обновление не происходит.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления calendar month изменяется в соответствии с минимальной; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов `SizeMinReq` успешно отображает элемент управления Календарь месяца для одного месяца календаря.

##  <a name="sizerecttomin"></a>  CMonthCalCtrl::SizeRectToMin

Для элемента управления calendar текущего месяца вычисляет наименьший прямоугольник, содержащий все календари, которые помещаются в заданном прямоугольнике.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpRect*|[in] Указатель на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, определяющая прямоугольник, содержащий требуемое число календарей.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, определяющая прямоугольник, размер которых меньше или равно в прямоугольник, определяемый *lpRect* параметра.

### <a name="remarks"></a>Примечания

Этот метод вычисляет, сколько календарей умещается в прямоугольник, определяемый *lpRect* параметра, а затем возвращает наименьший прямоугольник, который может содержать это число объектов календарей. По сути этот метод сжимает указанный прямоугольник точно по размеру требуемое число календарей.

Этот метод отправляет [MCM_SIZERECTTOMIN](/windows/desktop/Controls/mcm-sizerecttomin) сообщения, который описан в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Образец CMNCTRL1 MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)
