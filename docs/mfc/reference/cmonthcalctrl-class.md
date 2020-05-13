---
title: Класс CMonthCalCtrl
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
ms.openlocfilehash: 8c24c638d7006be112a53ec1e4f622ad528e348c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752814"
---
# <a name="cmonthcalctrl-class"></a>Класс CMonthCalCtrl

Инкапсулирует функциональность элемента управления "календарь месяца".

## <a name="syntax"></a>Синтаксис

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Формирует объект `CMonthCalCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMonthCalCtrl::Создание](#create)|Создает месячный календарный контроль и `CMonthCalCtrl` прикрепляет его к объекту.|
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Извлекает ширину границы календарного контроля текущего месяца.|
|[CMonthCalCtrl:GetCalendarCount](#getcalendarcount)|Извлекает количество календарей, отображаемых в элементе календарного управления текущего месяца.|
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Извлекает информацию о текущем элементе календарного контроля за текущим месяцем.|
|[CMonthCalCtrl:GetCalID](#getcalid)|Извлекает идентификатор календаря для управления календарем текущего месяца.|
|[CMonthCalCtrl::GetColor](#getcolor)|Получает цвет указанной области месячного календарного контроля.|
|[CMonthCalCtrl:GetCurrentView](#getcurrentview)|Извлекает представление, отображаемые в настоящее время в элементе управления календарем текущего месяца.|
|[CMonthCalCtrl:GetCurSel](#getcursel)|Извлекает время системы, указанное в выбранной в настоящее время дате.|
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Получает первый день недели, который будет отображаться в левой колонке календаря.|
|[CMonthCalCtrl:GetMaxSelCount](#getmaxselcount)|Извлекает текущее максимальное количество дней, которые могут быть выбраны в месячном календарном контроле.|
|[CMonthCalCtrl:GetMaxTodayWidth](#getmaxtodaywidth)|Извлекает максимальную ширину строки "Сегодня" для управления календарем текущего месяца.|
|[CMonthCalCtrl:GetMinReqRect](#getminreqrect)|Получает минимальный размер, необходимый для отображаемполный полный месяц в месячном календарном контроле.|
|[CMonthCalCtrl:GetMonthDelta](#getmonthdelta)|Извлекает скорость прокрутки для месячного календарного контроля.|
|[CMonthCalCtrl:GetMonthRange](#getmonthrange)|Извлекает информацию о дате, представляющую высокие и низкие пределы отображения элемента управления календарем месяца.|
|[CMonthCalCtrl:GetRange](#getrange)|Извлекает текущий минимум и максимальные даты, установленные в месячном календарном контроле.|
|[CMonthCalCtrl:GetSelRange](#getselrange)|Извлекает информацию о дате, представляющую верхние и нижние пределы диапазона дат, выбранных в настоящее время пользователем.|
|[CMonthCalCtrl:GetToday](#gettoday)|Извлекает информацию о дате для даты, указанной как "сегодня" для месячного календарного контроля.|
|[CMonthCalCtrl:HitTest](#hittest)|Определяет, какой раздел месячного календарного управления находится в данной точке на экране.|
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Указывает, является ли текущее представление текущего календарного контроля текущего месяца представлением столетия.|
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Указывает, является ли текущее представление элемента календарного управления текущего месяца представлением десятилетия.|
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Указывает, является ли текущее представление элемента календарного управления текущего месяца представлением месяца.|
|[CMonthCalCtrl::IsYearView](#isyearview)|Указывает, является ли текущее представление элемента календарного управления текущего месяца представлением года.|
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Устанавливает ширину границы календарного контроля текущего месяца.|
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Устанавливает ширину границы текущего месяца.|
|[CMonthCalCtrl:SetCalID](#setcalid)|Устанавливает идентификатор календаря для управления календарем текущего месяца.|
|[CMonthCalCtrl:SetCenturyView](#setcenturyview)|Устанавливает контроль календаря текущего месяца для отображения представления века.|
|[CMonthCalCtrl::SetColor](#setcolor)|Устанавливает цвет заданной области месячного календарного контроля.|
|[CMonthCalCtrl:SetCurrentView](#setcurrentview)|Устанавливает элемент управления календарем текущего месяца для отображения указанного представления.|
|[CMonthCalCtrl::SetCurSel](#setcursel)|Устанавливает выбранную в настоящее время дату для месячного календарного контроля.|
|[CMonthCalCtrl:SetDayState](#setdaystate)|Устанавливает дисплей в течение дней в месячном календарном контроле.|
|[CMonthCalCtrl:SetDecadeView](#setdecadeview)|Устанавливает контроль календаря текущего месяца в представлении десятилетия.|
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Устанавливает день недели, который будет отображаться в левой колонке календаря.|
|[CMonthCalCtrl:SetMaxSelCount](#setmaxselcount)|Устанавливает максимальное количество дней, которые могут быть выбраны в месячном календарном контроле.|
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Устанавливает скорость прокрутки для месячного календарного контроля.|
|[CMonthCalCtrl:SetMonthView](#setmonthview)|Устанавливает элемент управления календарем текущего месяца для отображения представления месяца.|
|[CMonthCalCtrl:SetRange](#setrange)|Устанавливает минимальные и максимально допустимые даты для месячного календарного контроля.|
|[CMonthCalCtrl:SetSelRange](#setselrange)|Устанавливает выбор для месячного календарного контроля в заданный диапазон даты.|
|[CMonthCalCtrl:SetToday](#settoday)|Устанавливает элемент управления календаря на текущий день.|
|[CMonthCalCtrl:SetYearView](#setyearview)|Устанавливает контроль календаря текущего месяца в виде года.|
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|Перерисовывает контроль календаря месяца до минимального, месячного размера.|
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Для управления календарем текущего месяца вычисляется наименьший прямоугольник, который может содержать все календари, которые вписываются в указанный прямоугольник.|

## <a name="remarks"></a>Remarks

Управление календарем месяца предоставляет пользователю простой интерфейс календаря, из которого пользователь может выбрать дату. Пользователь может изменить дисплей:

- Прокрутка назад и вперед, от месяца к месяцу.

- Нажав на текст Today для отображения текущего дня (если MCS_NOTODAY стиль не используется).

- Выбор месяца или года из всплывающее меню.

Вы можете настроить управление календарем месяца, применяя различные стили к объекту при его создании. Эти стили описаны в [стилях управления календарем месяцев](/windows/win32/Controls/month-calendar-control-styles) в Windows SDK.

Контроль календаря месяца может отображаться более одного месяца, и он может указывать специальные дни (например, праздники), смазав дату.

Для получения дополнительной информации об использовании элемента управления календарем месяца [см.](../../mfc/using-cmonthcalctrl.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxdtctl.h

## <a name="cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a>CMonthCalCtrl::CMonthCalCtrl

Формирует объект `CMonthCalCtrl`.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Remarks

Вы должны `Create` позвонить после построения объекта.

## <a name="cmonthcalctrlcreate"></a><a name="create"></a>CMonthCalCtrl::Создание

Создает месячный календарный контроль и `CMonthCalCtrl` прикрепляет его к объекту.

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
Определяет сочетание стилей Windows, применяемых к управлению календарем месяца. Для получения дополнительной информации о стилях можно ознакомиться с [«Стилями управления календарем месяца»](/windows/win32/Controls/month-calendar-control-styles) в SDK Windows.

*rect*<br/>
Ссылка на структуру [RECT.](/windows/win32/api/windef/ns-windef-rect) Содержит положение и размер месячного календарного элемента.

*пт*<br/>
Ссылка на структуру [POINT,](/windows/win32/api/windef/ns-windef-point) которая определяет местоположение элемента календарного управления месяца.

*pParentWnd*<br/>
Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном элемента календарного управления месяца. Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор управления контролем календаря месяца.

### <a name="return-value"></a>Возвращаемое значение

Незерно, если инициализация была успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Создайте месячный календарный контроль в два этапа:

1. Позвоните [CMonthCalCtrl,](../../mfc/reference/cmonthcalctrl-class.md) чтобы построить `CMonthCalCtrl` объект.

1. Вызов эту функцию участника, которая создает месячный `CMonthCalCtrl` элемент календарного управления и прикрепляет его к объекту.

При вызове `Create`общие элементы управления инициализированы. Версия `Create` вызова определяет размер:

- Чтобы MFC автоматически размер управления до одного месяца, позвоните переопределение, которое использует параметр *pt.*

- Чтобы размер элемента управления, позвоните переопределение этой функции, которая использует параметр *rect.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

## <a name="cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a>CMonthCalCtrl::GetCalendarBorder

Извлекает ширину границы календарного контроля текущего месяца.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина границы управления, в пикселях.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder) сообщение, которое описано в SDK Windows.

## <a name="cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a>CMonthCalCtrl:GetCalendarCount

Извлекает количество календарей, отображаемых в элементе календарного управления текущего месяца.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество календарей, отображаемых в настоящее время в элементе календаря месяца. Максимально допустимое количество календарей составляет 12.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount) сообщение, которое описано в SDK Windows.

## <a name="cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a>CMonthCalCtrl::GetCalendarGridInfo

Извлекает информацию о текущем элементе календарного контроля за текущим месяцем.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pmcGridInfo*|(ваут) Указатель на структуру [MCGRIDINFO,](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo) которая получает информацию о контроле календаря текущего месяца. Звонящий отвечает за выделение и инициализацию этой структуры.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_monthCalCtrl`переменную, которая используется для программного доступа к управлению календарем месяца. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере `GetCalendarGridInfo` кода используется метод для получения даты календаря, отображается в текущем месяце календарного управления.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

## <a name="cmonthcalctrlgetcalid"></a><a name="getcalid"></a>CMonthCalCtrl:GetCalID

Извлекает идентификатор календаря для управления календарем текущего месяца.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одна из констант [идентификатора календаря.](/windows/win32/Intl/calendar-identifiers)

### <a name="remarks"></a>Remarks

Идентификатор календаря обозначает календарь, специфичный для конкретного региона, например григорианский (локализованный), японский или хиджрский календари. Приложение может использовать идентификатор календаря с различными функциями поддержки языка.

Этот метод отправляет [MCM_GETCALID](/windows/win32/Controls/mcm-getcalid) сообщение, которое описано в SDK Windows.

## <a name="cmonthcalctrlgetcolor"></a><a name="getcolor"></a>CMonthCalCtrl::GetColor

Извлекает цвет области месячного календарного контроля, указанной *nRegion.*

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Параметры

*nРегион*<br/>
Область месячного календарного контроля, из которого извлекается цвет. Список значений см. *nRegion* [SetColor](#setcolor)

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) определяющее цвет, связанный с частью месячного календарного элемента, в случае успеха. В противном случае эта функция участника возвращает -1.

## <a name="cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a>CMonthCalCtrl:GetCurrentView

Извлекает представление, отображаемые в настоящее время в элементе управления календарем текущего месяца.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее представление, которое указывается одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|MCMV_MONTH|Ежемесячное представление|
|MCMV_YEAR|Годовой просмотр|
|MCMV_DECADE|Представление десятилетия|
|MCMV_CENTURY|Вид на столетие|

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_monthCalCtrl`переменную, которая используется для программного доступа к управлению календарем месяца. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

Следующий пример кода сообщает, который просматривает элемент управления календарем месяца в настоящее время отображается.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

## <a name="cmonthcalctrlgetcursel"></a><a name="getcursel"></a>CMonthCalCtrl:GetCurSel

Извлекает время системы, указанное в выбранной в настоящее время дате.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или объект [CTime.](../../atl-mfc-shared/reference/ctime-class.md) Получает текущее время.

*pDateTime*<br/>
Указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) которая будет получать выбранную в настоящее время информацию о дате. Этот параметр должен быть действительным адресом и не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; otherwize 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETCURSEL,](/windows/win32/Controls/mcm-getcursel)как описано в SDK Windows.

> [!NOTE]
> Эта функция участника выходит из строя, если установлен MCS_MULTISELECT стиля.

При `GetCurSel`реализации MFC можно указать `COleDateTime` использование, `CTime` использование или `SYSTEMTIME` использование структуры.

## <a name="cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a>CMonthCalCtrl::GetFirstDayOfWeek

Получает первый день недели, который будет отображаться в левой колонке календаря.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Параметры

*pbLocal*<br/>
Указатель на значение BOOL. Если значение не является нулевым, настройка элемента управления не соответствует настройке панели управления.

### <a name="return-value"></a>Возвращаемое значение

Значение, которое представляет собой первый день недели. Смотрите **Замечания** для получения дополнительной информации о том, что эти числа представляют.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETFIRSTDAYOFWEEK,](/windows/win32/Controls/mcm-getfirstdayofweek)как описано в SDK Windows. Дни недели представлены как целые числа, а именно.

|Значение|День недели|
|-----------|---------------------|
|0|Понедельник|
|1|Вторник|
|2|Среда|
|3|Четверг|
|4|Пятница|
|5|Суббота|
|6|Воскресенье|

### <a name="example"></a>Пример

  Смотрите пример [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek).

## <a name="cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a>CMonthCalCtrl:GetMaxSelCount

Извлекает текущее максимальное количество дней, которые могут быть выбраны в месячном календарном контроле.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение целых, которое представляет общее количество дней, которые могут быть выбраны для управления.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMAXSELCOUNT,](/windows/win32/Controls/mcm-getmaxselcount)как описано в SDK Windows. Используйте эту функцию элемента для управления с набором MCS_MULTISELECT стилем.

### <a name="example"></a>Пример

  Смотрите пример [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount).

## <a name="cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a>CMonthCalCtrl:GetMaxTodayWidth

Извлекает максимальную ширину строки "Сегодня" для управления календарем текущего месяца.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина строки "Сегодня" в пикселях.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_monthCalCtrl`переменную, которая используется для программного доступа к управлению календарем месяца. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

Следующий пример кода `GetMaxTodayWidth` демонстрирует метод.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Remarks

Пользователь может вернуться к текущей дате, нажав строку "Сегодня", которая отображается в нижней части элемента календарного управления месяца. Строка "Сегодня" включает текст метки и текст даты.

Этот метод отправляет [MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth) сообщение, которое описано в SDK Windows.

## <a name="cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a>CMonthCalCtrl:GetMinReqRect

Получает минимальный размер, необходимый для отображаемполный полный месяц в месячном календарном контроле.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Параметры

*pRect*<br/>
Указатель на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) которая будет получать информацию о прямоугольнике. Этот параметр должен быть действительным адресом и не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха эта функция `lpRect` участника возвращает ненулевой и получает соответствующую информацию о границах. В случае неудачи функция участника возвращает 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMINREQRECT,](/windows/win32/Controls/mcm-getminreqrect)как описано в SDK Windows.

## <a name="cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a>CMonthCalCtrl:GetMonthDelta

Извлекает скорость прокрутки для месячного календарного контроля.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Возвращаемое значение

Скорость прокрутки для месячного календарного контроля. Скорость прокрутки — это количество месяцев, в течение которого элемент управления перемещает свой дисплей, когда пользователь один раз нажимает кнопку прокрутки.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMONTHDELTA,](/windows/win32/Controls/mcm-getmonthdelta)как описано в SDK Windows.

## <a name="cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a>CMonthCalCtrl:GetMonthRange

Извлекает информацию о дате, представляющую высокие и низкие пределы отображения элемента управления календарем месяца.

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
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий разрешенную минимальную дату.

*refMaxRange*<br/>
Ссылка на `COleDateTime` `CTime` объект или объект, содержащий разрешенную максимальную дату.

*pMinRange*<br/>
Указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую дату в самом нижнем конце диапазона.

*pMaxRange*<br/>
Указатель на `SYSTEMTIME` структуру, содержащую дату на самом высоком конце диапазона.

*dwFlags*<br/>
Значение, определяющее область предельных значений, которые необходимо получить. Это значение должно быть одним из следующих.

|Значение|Значение|
|-----------|-------------|
|GMR_DAYSTATE|Включите предыдущие и задние месяцы видимого диапазона, которые отображаются лишь частично.|
|GMR_VISIBLE|Включите только те месяцы, которые полностью отображаются.|

### <a name="return-value"></a>Возвращаемое значение

Целый ряд, который представляет диапазон, в месяцах, охватывает два предела, указанные *refMinRange* и *refMaxRange* в первой и второй версии, или *pMinRange* и *pMaxRange* в третьей версии.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMONTHRANGE,](/windows/win32/Controls/mcm-getmonthrange)как описано в SDK Windows. При `GetMonthRange`реализации MFC можно указать `COleDateTime` использование, `CTime` использование `SYSTEMTIME` или использование структуры.

### <a name="example"></a>Пример

  Смотрите пример [CMonthCalCtrl::SetDayState](#setdaystate).

## <a name="cmonthcalctrlgetrange"></a><a name="getrange"></a>CMonthCalCtrl:GetRange

Извлекает текущий минимум и максимальные даты, установленные в месячном календарном контроле.

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
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую дату в нижнем конце диапазона.

*pMaxRange*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую дату на самом высоком конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

DWORD, который может быть нулевым (не устанавливаются ограничения) или комбинация следующих значений, которые указывают информацию о пределе.

|Значение|Значение|
|-----------|-------------|
|GDTR_MAX|Для элемента управления установлен максимальный предел; *pMaxRange* действителен и содержит соответствующую информацию о дате.|
|GDTR_MIN|Для элемента управления устанавливается минимальный лимит; *pMinRange* действителен и содержит соответствующую информацию о дате.|

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETRANGE,](/windows/win32/Controls/mcm-getrange)как описано в SDK Windows. При `GetRange`реализации MFC можно указать `COleDateTime` использование, `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

## <a name="cmonthcalctrlgetselrange"></a><a name="getselrange"></a>CMonthCalCtrl:GetSelRange

Извлекает информацию о дате, представляющую верхние и нижние пределы диапазона дат, выбранных в настоящее время пользователем.

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
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий разрешенную минимальную дату.

*refMaxRange*<br/>
Ссылка на `COleDateTime` `CTime` объект или объект, содержащий разрешенную максимальную дату.

*pMinRange*<br/>
Указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую дату в самом нижнем конце диапазона.

*pMaxRange*<br/>
Указатель на `SYSTEMTIME` структуру, содержащую дату на самом высоком конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETSELRANGE,](/windows/win32/Controls/mcm-getselrange)как описано в SDK Windows. `GetSelRange`не удастся, если применить к месячному календарному управлению, который не использует MCS_MULTISELECT стиль.

При `GetSelRange`реализации MFC можно указать `COleDateTime` использование, `CTime` использование `SYSTEMTIME` или использование структуры.

## <a name="cmonthcalctrlgettoday"></a><a name="gettoday"></a>CMonthCalCtrl:GetToday

Извлекает информацию о дате для даты, указанной как "сегодня" для месячного календарного контроля.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) с указанием текущего дня.

*pDateTime*<br/>
Указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) которая будет получать информацию о дате. Этот параметр должен быть действительным адресом и не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_GETTODAY,](/windows/win32/Controls/mcm-gettoday)как описано в SDK Windows. При `GetToday`реализации MFC можно указать `COleDateTime` использование, `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

## <a name="cmonthcalctrlhittest"></a><a name="hittest"></a>CMonthCalCtrl:HitTest

Определяет, какой месячный календарный контроль, если таковой имеется, находится в определенной позиции.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Параметры

*pMCHitTest*<br/>
Указатель на структуру [MCHITTESTINFO,](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo) содержащую точки тестирования для управления календарем месяца.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD. Равно **uHit** член `MCHITTESTINFO` структуры.

### <a name="remarks"></a>Remarks

`HitTest`использует `MCHITTESTINFO` структуру, которая содержит информацию о хит-тесте.

## <a name="cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a>CMonthCalCtrl::IsCenturyView

Указывает, является ли текущее представление текущего календарного контроля текущего месяца представлением столетия.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если текущее мнение века зрения; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, которое описано в SDK Windows. Если это сообщение возвращает MCMV_CENTURY, этот метод возвращает TRUE.

## <a name="cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a>CMonthCalCtrl::IsDecadeView

Указывает, является ли текущее представление элемента календарного управления текущего месяца представлением десятилетия.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если текущее представление является десятилетие зрения; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, которое описано в SDK Windows. Если это сообщение возвращается MCMV_DECADE, этот метод возвращает TRUE.

## <a name="cmonthcalctrlismonthview"></a><a name="ismonthview"></a>CMonthCalCtrl::IsMonthView

Указывает, является ли текущее представление элемента календарного управления текущего месяца представлением месяца.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если текущее представление представляет собой представление месяца; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, которое описано в SDK Windows. Если это сообщение возвращает MCMV_MONTH, этот метод возвращает TRUE.

## <a name="cmonthcalctrlisyearview"></a><a name="isyearview"></a>CMonthCalCtrl::IsYearView

Указывает, является ли текущее представление элемента календарного управления текущего месяца представлением года.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если текущее представление представляет собой представление года; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, которое описано в SDK Windows. Если это сообщение возвращается MCMV_YEAR, этот метод возвращает TRUE.

## <a name="cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a>CMonthCalCtrl::SetCalendarBorder

Устанавливает ширину границы календарного контроля текущего месяца.

```cpp
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*cxyBorder*|(в) Ширина границы, в пикселях.|

### <a name="remarks"></a>Remarks

Если этот метод удается, ширина границы устанавливается на параметр *cxyBorder.* В противном случае ширина границы сброшена на значение по умолчанию, указанное текущей [темой,](/windows/win32/Controls/visual-styles-overview)или ноль, если темы не используются.

Этот метод отправляет [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_monthCalCtrl`переменную, которая используется для программного доступа к управлению календарем месяца. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает ширину границы управления календарем месяца до восьми пикселей. Используйте метод [CMonthCalCtrl::GetCalendarBorder,](#getcalendarborder) чтобы определить, удалось ли этому методу.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

## <a name="cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a>CMonthCalCtrl::SetCalendarBorderDefault

Устанавливает ширину границы текущего месяца.

```cpp
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Remarks

Ширина границы устанавливается на значение по умолчанию, указанное текущей [темой,](/windows/win32/Controls/visual-styles-overview)или ноль, если темы не используются.

Этот метод отправляет [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) сообщение, которое описано в SDK Windows.

## <a name="cmonthcalctrlsetcalid"></a><a name="setcalid"></a>CMonthCalCtrl:SetCalID

Устанавливает идентификатор календаря для управления календарем текущего месяца.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*калид*|(в) Одна из констант [идентификатора календаря.](/windows/win32/Intl/calendar-identifiers)|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Идентификатор календаря определяет календарь, специфичный для конкретного региона, например григорианский (локализованный), японский или хиджрский календари. Используйте `SetCalID` метод для отображения календаря, указанного параметром *calid,* если локали, содержащее календарь, установлен на вашем компьютере.

Этот метод отправляет [MCM_SETCALID](/windows/win32/Controls/mcm-setcalid) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_monthCalCtrl`переменную, которая используется для программного доступа к управлению календарем месяца. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает контроль календаря месяца для отображения календаря эпохи японского императора. Метод `SetCalID` удается только в том случае, если этот календарь установлен на вашем компьютере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

## <a name="cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a>CMonthCalCtrl:SetCenturyView

Устанавливает контроль календаря текущего месяца для отображения представления века.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод использует [cMonthCalCtrl::SetCurrentView](#setcurrentview) метод для `MCMV_CENTURY`установки представления, который представляет представление века.

## <a name="cmonthcalctrlsetcolor"></a><a name="setcolor"></a>CMonthCalCtrl::SetColor

Устанавливает цвет заданной области месячного календарного контроля.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Параметры

*nРегион*<br/>
Значение, определяющее цвет календаря за месяц. Это значение может быть одним из следующих.

|Значение|Значение|
|-----------|-------------|
|MCSC_BACKGROUND|Цвет фона отображается между месяцами.|
|MCSC_MONTHBK|Цвет фона отображается в течение месяца.|
|MCSC_TEXT|Цвет, используемый для отображения текста в течение месяца.|
|MCSC_TITLEBK|Цвет фона отображается в заголовке календаря.|
|MCSC_TITLETEXT|Цвет, используемый для отображения текста в заголовке календаря.|
|MCSC_TRAILINGTEXT|Цвет, используемый для отображения заголовка и задней день текста. Заголовки и задние дни являются днями предыдущих и последующих месяцев, которые отображаются в текущем календаре.|

*ref*<br/>
Значение COLORREF для нового параметра цвета для заданной части месячного календарного элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее предыдущую настройку цвета для заданной части элемента календарного управления месяца, в случае успеха. В противном случае это сообщение возвращается -1.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETCOLOR,](/windows/win32/Controls/mcm-setcolor)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

## <a name="cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a>CMonthCalCtrl:SetCurrentView

Устанавливает элемент управления календарем текущего месяца для отображения указанного представления.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwNewView*|(в) Одно из следующих значений, которое определяет ежемесячное, ежегодное, десятилетие или столетие зрения.<br /><br /> MCMV_MONTH: Ежемесячное представление<br /><br /> MCMV_YEAR: Ежегодный просмотр<br /><br /> MCMV_DECADE: Представление десятилетия<br /><br /> MCMV_CENTURY: Вид века|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview) сообщение, которое описано в SDK Windows.

## <a name="cmonthcalctrlsetcursel"></a><a name="setcursel"></a>CMonthCalCtrl::SetCurSel

Устанавливает выбранную в настоящее время дату для месячного календарного контроля.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) с указанием выбранного в настоящее время элемента календарного управления месяцем.

*pDateTime*<br/>
Указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую дату, которая будет установлена в качестве текущего выбора.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETCURSEL,](/windows/win32/Controls/mcm-setcursel)как описано в SDK Windows. При `SetCurSel`реализации MFC можно указать `COleDateTime` использование, `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

## <a name="cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a>CMonthCalCtrl:SetDayState

Устанавливает дисплей в течение дней в месячном календарном контроле.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Параметры

*nМесяцы*<br/>
Значение, указывающее, сколько элементов в массиве, на который указывают *pstates.*

*pstates*<br/>
Указатель на массив значений [MONTHDAYSTATE,](/windows/win32/Controls/monthdaystate) определяющий, как контроль календаря месяца будет рисовать каждый день в своем дисплее. Тип данных MONTHDAYSTATE — это поле немного, где каждый бит (от 1 до 31) представляет состояние дня в месяц. Если немного на, соответствующий день будет отображаться жирным шрифтом; в противном случае он будет отображаться без акцента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETDAYSTATE,](/windows/win32/Controls/mcm-setdaystate)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

## <a name="cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a>CMonthCalCtrl:SetDecadeView

Устанавливает контроль календаря текущего месяца в представлении десятилетия.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод использует метод [CMonthCalCtrl::SetCurrentView](#setcurrentview) для `MCMV_DECADE`настройки представления, представляющего представление десятилетия.

## <a name="cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a>CMonthCalCtrl::SetFirstDayOfWeek

Устанавливает день недели, который будет отображаться в левой колонке календаря.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Параметры

*iDay*<br/>
Целый номер значения, представляющие, какой день должен быть установлен в качестве первого дня недели. Это значение должно быть одним из дневных чисел. Ознакомьтесь с номерами [GetFirstDayOfWeek.](#getfirstdayofweek)

*lpnOld*<br/>
Указатель на множество с указанием первого дня недели, ранее установленного.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если предыдущий первый день недели установлен на значение, кроме LOCALE_IFIRSTDAYOFWEEK, который является днем, указанным в настройках панели управления. В противном случае эта функция возвращает 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETFIRSTDAYOFWEEK,](/windows/win32/Controls/mcm-setfirstdayofweek)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

## <a name="cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a>CMonthCalCtrl:SetMaxSelCount

Устанавливает максимальное количество дней, которые могут быть выбраны в месячном календарном контроле.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Параметры

*nMax*<br/>
Значение, которое будет установлено для представления максимального количества выбранных дней.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETMAXSELCOUNT,](/windows/win32/Controls/mcm-setmaxselcount)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

## <a name="cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a>CMonthCalCtrl::SetMonthDelta

Устанавливает скорость прокрутки для месячного календарного контроля.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Параметры

*iDelta*<br/>
Количество месяцев, которые будут установлены в качестве скорости прокрутки элемента. Если это значение равен нулю, дельта месяца сбросируется на значение по умолчанию, т.е. количество месяцев, отображаемых в элементе управления.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая скорость прокрутки. Если скорость прокрутки не была установлена ранее, значение возврата составляет 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETMONTHDELTA,](/windows/win32/Controls/mcm-setmonthdelta)как описано в SDK Windows.

## <a name="cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a>CMonthCalCtrl:SetMonthView

Устанавливает элемент управления календарем текущего месяца для отображения представления месяца.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод использует метод [CMonthCalCtrl::SetCurrentView](#setcurrentview) для установки представления для MCMV_MONTH, который представляет представление месяца.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_monthCalCtrl`переменную, которая используется для программного доступа к управлению календарем месяца. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода устанавливается элемент управления календарем месяца для отображения представлений за месяц, год, десятилетие и столетие.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

## <a name="cmonthcalctrlsetrange"></a><a name="setrange"></a>CMonthCalCtrl:SetRange

Устанавливает минимальные и максимально допустимые даты для месячного календарного контроля.

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
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую дату в нижнем конце диапазона.

*pMaxRange*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или `SYSTEMTIME` структуру, содержащую дату на самом высоком конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETRANGE,](/windows/win32/Controls/mcm-setrange)как описано в SDK Windows. При `SetRange`реализации MFC можно указать `COleDateTime` использование, `CTime` использование `SYSTEMTIME` или использование структуры.

### <a name="example"></a>Пример

  Смотрите пример [cMonthCalCtrl::GetRange](#getrange).

## <a name="cmonthcalctrlsetselrange"></a><a name="setselrange"></a>CMonthCalCtrl:SetSelRange

Устанавливает выбор для месячного календарного контроля в заданный диапазон даты.

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
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую дату в нижнем конце диапазона.

*pMaxRange*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или `SYSTEMTIME` структуру, содержащую дату на самом высоком конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция-член реализует поведение сообщения Win32 [MCM_SETSELRANGE,](/windows/win32/Controls/mcm-setselrange)как описано в SDK Windows. При `SetSelRange`реализации MFC можно указать `COleDateTime` использование, `CTime` использование `SYSTEMTIME` или использование структуры.

## <a name="cmonthcalctrlsettoday"></a><a name="settoday"></a>CMonthCalCtrl:SetToday

Устанавливает элемент управления календаря на текущий день.

```cpp
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Параметры

*refDateTime*<br/>
Ссылка на объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий текущую дату.

*pDateTime*<br/>
Во второй версии указатель на объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий текущую информацию о дате. В третьей версии указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую текущую информацию о дате.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [MCM_SETTODAY,](/windows/win32/Controls/mcm-settoday)как описано в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CMonthCalCtrl::GetToday](#gettoday).

## <a name="cmonthcalctrlsetyearview"></a><a name="setyearview"></a>CMonthCalCtrl:SetYearView

Устанавливает контроль календаря текущего месяца в виде года.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод использует метод [CMonthCalCtrl::SetCurrentView](#setcurrentview) для установки представления для MCMV_YEAR, который представляет годовой вид.

## <a name="cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a>CMonthCalCtrl::SizeMinReq

Отображает элемент управления календарем месяца до минимального размера, который отображает один месяц.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Параметры

*bRepaint*<br/>
Определяет, следует ли перекрасить элемент управления. По умолчанию, ПРАВДА. Если FALSE, не происходит перекрашивания.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если контроль календаря месяца размером до минимума; в противном случае 0.

### <a name="remarks"></a>Remarks

Вызов `SizeMinReq` успешно отображает весь элемент календарного управления месяца для календаря за один месяц.

## <a name="cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a>CMonthCalCtrl::SizeRectToMin

Для управления календарем текущего месяца вычисляется наименьший прямоугольник, который может содержать все календари, которые вписываются в указанный прямоугольник.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpRect*|(в) Указатель на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющую прямоугольник, содержащий нужное количество календарей.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющую прямоугольник, размер которого меньше или равен прямоугольнику, определяемому параметром *lpRect.*

### <a name="remarks"></a>Remarks

Этот метод вычисляет, сколько календарей может поместиться в прямоугольник, указанный параметром *lpRect,* а затем возвращает наименьший прямоугольник, который может содержать это количество календарей. По сути, этот метод сжимает указанный прямоугольник, чтобы точно соответствовать желаемому количеству календарей.

Этот метод отправляет [MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin) сообщение, которое описано в SDK Windows.

## <a name="see-also"></a>См. также раздел

[MFC Образец CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)
