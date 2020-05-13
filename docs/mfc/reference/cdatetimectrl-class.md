---
title: Класс CDateTimeCtrl
ms.date: 11/04/2016
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
ms.openlocfilehash: 577dde7f4f4209f15590825fdb87fe23f788a1ce
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754613"
---
# <a name="cdatetimectrl-class"></a>Класс CDateTimeCtrl

Инкапсулирует функциональность элемента управления "выбор даты и времени".

## <a name="syntax"></a>Синтаксис

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Формирует объект `CDateTimeCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Закрывает текущий контроль времени и времени сборщика.|
|[CDateTimeCtrl::Создание](#create)|Создает управление сборщиком даты и времени `CDateTimeCtrl` и прикрепляет его к объекту.|
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Извлекает информацию о текущей дате и времени управления сборщика.|
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Возвращает идеальный размер управления сборщика даты и времени, который необходим для отображения текущей даты или времени.|
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Получает цвет для данной части месячного календаря в пределах контроля за датой и временем сборщика.|
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|Извлекает `CMonthCalCtrl` объект, связанный с управлением сборщика даты и времени.|
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Извлекает шрифт, используемый в настоящее время в управлении календарем детского месяца управления дочерним элементом насборщика данных.|
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Получает стиль текущего контроля надативную дату и время сборщика.|
|[CDateTimeCtrl:GetRange](#getrange)|Получает текущее минимальное и максимально допустимое время системы для управления сборщиком даты и времени.|
|[CDateTimeCtrl::GetTime](#gettime)|Извлекает выбранное в настоящее время время из управления сборщика даты и времени и помещает его в заданную `SYSTEMTIME` структуру.|
|[CDateTimeCtrl::SetFormat](#setformat)|Устанавливает отображение управления сборщиком даты и времени в соответствии с заданной строкой формата.|
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Устанавливает цвет для заданной части месячного календаря в пределах контроля сборщика даты и времени.|
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|Устанавливает шрифт, который будет использовать элемент управления детского месяца управления датой и временем.|
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Устанавливает стиль текущего управления сборщиком даты и времени.|
|[CDateTimeCtrl:SetRange](#setrange)|Устанавливает минимальное и максимально допустимое время системы для управления сборщиком даты и времени.|
|[CDateTimeCtrl:SetTime](#settime)|Устанавливает время в контроле сборщика даты и времени.|

## <a name="remarks"></a>Remarks

Контроль навыборщика даты и времени (управление DTP) обеспечивает простой интерфейс для обмена информацией о дате и времени с пользователем. Этот интерфейс содержит поля, каждое из которых отображает часть информации о дате и времени, хранящейся в элементе управления. Пользователь может изменить информацию, хранящуюся в элементе управления, изменяя содержимое строки в заданном поле. Пользователь может перемещаться с поля на поле с помощью мыши или клавиатуры.

Вы можете настроить управление сборщиком даты и времени, применяя различные стили к объекту при его создании. Для получения дополнительной информации о стилях, характерных для управления сборщиком дат и времени, можно ознакомиться с стилями управления сборщиком данных [и времен.](/windows/win32/Controls/date-and-time-picker-control-styles) Вы можете настроить формат отображения управления DTP с помощью стилей формата. Эти стили формата описаны в "Формат стилей" в Теме Windows SDK [Дата и время Picker управления стили](/windows/win32/Controls/date-and-time-picker-control-styles).

Контроль насборщика даты и времени также использует уведомления и обратные вызовы, которые описаны в [использовании CDateTimeCtrl.](../../mfc/using-cdatetimectrl.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxdtctl.h

## <a name="cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl

Формирует объект `CDateTimeCtrl`.

```
CDateTimeCtrl();
```

## <a name="cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal

Закрывает текущий контроль времени и времени сборщика.

```cpp
void CloseMonthCal() const;
```

### <a name="remarks"></a>Remarks

Этот метод отправляет [DTM_CLOSEMONTHCAL](/windows/win32/Controls/dtm-closemonthcal) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_dateTimeCtrl,* которая используется для программного доступа к управлению сборщиком даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

Следующий пример кода закрывает календарь выпадения для текущего управления сборщиком даты и времени.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

## <a name="cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::Создание

Создает управление сборщиком даты и времени `CDateTimeCtrl` и прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет сочетание стилей контроля времени даты. Для получения дополнительной информации о стилях сборщика дат [и времени](/windows/win32/Controls/date-and-time-picker-control-styles) смотрите в SDK Windows для получения дополнительной информации о стилях сборщика дат и времени.

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) которая является положением и размером контроля насборщика даты и времени.

*pParentWnd*<br/>
Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном управления сборщиком даты и времени. Она не должна быть NULL.

*nID*<br/>
Упогоняет идентификатор управления элементом управления по дате и времени.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если создание было успешным; в противном случае 0.

### <a name="remarks"></a>Remarks

##### <a name="to-create-a-date-and-time-picker-control"></a>Создание управления сборщиком даты и времени

1. Позвоните [CDateTimeCtrl,](#cdatetimectrl) чтобы построить `CDateTimeCtrl` объект.

1. Вызов исключайте эту функцию участника, которая создает дату `CDateTimeCtrl` и управление сборщиком времени Windows и прикрепляет его к объекту.

При вызове `Create`общие элементы управления инициализированы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

## <a name="cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo

Извлекает информацию о текущей дате и времени управления сборщика.

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pDatePickerInfo*|(ваут) Указатель на структуру [DATETIMEPICKERINFO,](/windows/win32/api/commctrl/ns-commctrl-datetimepickerinfo) которая получает описание текущей даты и времени насборщика управления.<br /><br /> Звонящее отвечает за выделение этой структуры. Тем не менее, этот метод инициализирует *cbSize* член структуры.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [сообщение DTM_GETDATETIMEPICKERINFO,](/windows/win32/Controls/dtm-getdatetimepickerinfo) которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_dateTimeCtrl,* которая используется для программного доступа к управлению сборщиком даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

Следующий пример кода показывает, успешно ли он получает информацию о текущем управлении сборщиком даты и времени.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

## <a name="cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor

Получает цвет для данной части месячного календаря в пределах контроля за датой и временем сборщика.

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>Параметры

*iColor*<br/>
**Значение int,** определяющее, какую цветовую область календаря месяца получить. Список значений можно узнать на примере *iColor* для [SetMonthCalColor.](#setmonthcalcolor)

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее настройку цвета для заданной части месячного календарного элемента, если она будет успешной. Функция возвращается -1 в случае неудачи.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_GETMCCOLOR,](/windows/win32/Controls/dtm-getmccolor)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

## <a name="cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl

Извлекает `CMonthCalCtrl` объект, связанный с управлением сборщика даты и времени.

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) или NULL, если он не работает или если окно не видно.

### <a name="remarks"></a>Remarks

Элементы управления сборщиком дат и времени создают управление календарем детского месяца, когда пользователь нажимает на стрелку выпадения. Когда `CMonthCalCtrl` объект больше не нужен, он уничтожается, поэтому приложение не должно полагаться на хранение объекта, представляющего календарь детского месяца управления таймингом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

## <a name="cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont

Получает шрифт, используемый в настоящее время в управлении календарем месячного управления управления сборщиком даты и времени.

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CFont](../../mfc/reference/cfont-class.md) или NULL, если он не увенчался успехом.

### <a name="remarks"></a>Remarks

Объект, `CFont` на который указывает сятвое значение возврата, является временным объектом и уничтожается во время следующего простоя обработки.

## <a name="cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle

Получает стиль управления календарем месяца, связанный с текущей датой и контролем сборщика времени.

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Стиль управления календарем в течение месяца, который представляет собой битную комбинацию (OR) стилей управления сборщиком дат и времени. Для получения дополнительной [Month Calendar Control Styles](/windows/win32/Controls/month-calendar-control-styles)информации см.

### <a name="remarks"></a>Remarks

Этот метод отправляет [DTM_GETMCSTYLE](/windows/win32/Controls/dtm-getmcstyle) сообщение, которое описано в SDK Windows.

## <a name="cdatetimectrlgetrange"></a><a name="getrange"></a>CDateTimeCtrl:GetRange

Получает текущее минимальное и максимально допустимое время системы для управления сборщиком даты и времени.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>Параметры

*pMinRange*<br/>
Указатель на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий `CDateTimeCtrl` самое раннее время, разрешенное в объекте.

*pMaxRange*<br/>
Указатель на `COleDateTime` объект или `CTime` объект, содержащий последнее `CDateTimeCtrl` время, разрешенное в объекте.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее флаги, указывающие, какие диапазоны установлены. Если

`return value & GDTR_MAX` == 0

затем второй параметр действителен. Аналогичным образом, если

`return value & GDTR_MIN` == 0

затем первый параметр действителен.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_GETRANGE,](/windows/win32/Controls/dtm-getrange)как описано в SDK Windows. В реализации MFC можно указать либо `COleDateTime` `CTime` или обычаи.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

## <a name="cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::GetTime

Извлекает выбранное в настоящее время время из управления сборщика даты и времени и помещает его в заданную `SYSTEMTIME` структуру.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Параметры

*timeDest*<br/>
В первой версии ссылка на объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) который будет получать информацию о времени системы. Во второй версии ссылка на объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) который будет получать информацию о времени системы.

*pTimeDest*<br/>
Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения информации о времени системы. Не должно быть NULL.

### <a name="return-value"></a>Возвращаемое значение

В первой версии, ненулевой, если `COleDateTime` время успешно написано на объект; в противном случае 0. Во второй и третьей версиях значение DWORD, равное члену *dwFlag,* установленное в структуре [NMDATETIMECHANGE.](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) Для получения дополнительной информации ниже приведен раздел **«Замечания».**

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_GETSYSTEMTIME,](/windows/win32/Controls/dtm-getsystemtime)как описано в SDK Windows. В `GetTime`реализации MFC, вы `COleDateTime` `CTime` можете использовать или классов, или вы можете использовать структуру, `SYSTEMTIME` для хранения информации о времени.

Значение возврата DWORD во второй и третьей версиях, выше, указывает, является ли дата и время управления сборщика установлен на "нет даты" статус, как указано в [nMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) структуры члена *dwFlags*. Если возвратное значение равно GDT_NONE, элемент управления устанавливается в статусе "без даты" и использует DTS_SHOWNONE стиль. Если возврат номинал равняется GDT_VALID, время системы успешно хранится в месте назначения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

## <a name="cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize

Возвращает идеальный размер управления сборщика даты и времени, который необходим для отображения текущей даты или времени.

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*psize*|(ваут) Указатель на структуру [СИЗЕ,](/windows/win32/api/windef/ns-windef-size) которая содержит идеальный размер для управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение возврата всегда верно.

### <a name="remarks"></a>Remarks

Этот метод отправляет [DTM_GETIDEALSIZE](/windows/win32/Controls/dtm-getidealsize) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_dateTimeCtrl,* которая используется для программного доступа к управлению сборщиком даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

Следующий пример кода получает идеальный размер для отображения управления сборщиком даты и времени.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

## <a name="cdatetimectrlsetformat"></a><a name="setformat"></a>CDateTimeCtrl::SetFormat

Устанавливает отображение управления сборщиком даты и времени в соответствии с заданной строкой формата.

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>Параметры

*стр.Формат*<br/>
Указатель на строку формата с нулевым завершением, определяющую нужный дисплей. Установка этого параметра в NULL сброс элемента управления в строку формата по умолчанию для текущего стиля.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

> [!NOTE]
> Пользовательский ввод не определяет успех или сбой для этого вызова.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_SETFORMAT,](/windows/win32/Controls/dtm-setformat)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

## <a name="cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor

Устанавливает цвет для заданной части месячного календаря в пределах контроля сборщика даты и времени.

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>Параметры

*iColor*<br/>
**значение int,** определяющее, какую область элемента календаря месяца установить. Это значение может быть одним из следующих.

|Значение|Значение|
|-----------|-------------|
|MCSC_BACKGROUND|Установите цвет фона отображается между месяцами.|
|MCSC_MONTHBK|Установите цвет фона отображается в течение месяца.|
|MCSC_TEXT|Установите цвет, используемый для отображения текста в течение месяца.|
|MCSC_TITLEBK|Установите цвет фона, отображаемый в заголовке календаря.|
|MCSC_TITLETEXT|Установите цвет, используемый для отображения текста в заголовке календаря.|
|MCSC_TRAILINGTEXT|Установите цвет, используемый для отображения заголовка и задней день текста. Заголовки и задние дни являются днями предыдущих и последующих месяцев, которые отображаются в текущем календаре.|

*ref*<br/>
Значение COLORREF, представляющее цвет, который будет установлен для указанной области месячного календаря.

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее предыдущую настройку цвета для заданной части месячного календарного элемента, если она будет успешной. В противном случае сообщение возвращается -1.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_SETMCCOLOR,](/windows/win32/Controls/dtm-setmccolor)как описано в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [Для CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).

## <a name="cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont

Устанавливает шрифт, который будет использовать элемент управления детского месяца управления датой и временем.

```cpp
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*hFont*<br/>
Ручка к шрифту, который будет установлен.

*bRedraw*<br/>
Уточняется, следует ли перенарисовать элемент управления сразу же после установки шрифта. Установка этого параметра на TRUE вызывает элемент управления, чтобы перерисовать себя.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_SETMCFONT,](/windows/win32/Controls/dtm-setmcfont)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
> Если вы используете этот код, вы хотите `CDialog`сделать члена вашего `CFont`класса, полученного под названием *m_MonthFont* типа.

## <a name="cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle

Устанавливает стиль управления календарем месяца, связанного с текущим управлением сборщиком дат и времени.

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwStyle*|(в) Новый стиль управления календарем месяца, который является билистой комбинацией (OR) стилей управления календарем месяца. Для получения дополнительной [Month Calendar Control Styles](/windows/win32/Controls/month-calendar-control-styles)информации см.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий стиль управления календарем займом в месяц.

### <a name="remarks"></a>Remarks

Этот метод отправляет [DTM_SETMCSTYLE](/windows/win32/Controls/dtm-setmcstyle) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_dateTimeCtrl,* которая используется для программного доступа к управлению сборщиком даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

В следующем примере кода устанавливается контроль за датой и временем выбора для отображения недельных номеров, сокращенных названий дней недели и индикатора «сегодня нет».

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

## <a name="cdatetimectrlsetrange"></a><a name="setrange"></a>CDateTimeCtrl:SetRange

Устанавливает минимальное и максимально допустимое время системы для управления сборщиком даты и времени.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>Параметры

*pMinRange*<br/>
Указатель на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий `CDateTimeCtrl` самое раннее время, разрешенное в объекте.

*pMaxRange*<br/>
Указатель на `COleDateTime` объект или `CTime` объект, содержащий последнее `CDateTimeCtrl` время, разрешенное в объекте.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_SETRANGE,](/windows/win32/Controls/dtm-setrange)как описано в SDK Windows. В реализации MFC можно указать либо `COleDateTime` `CTime` или обычаи. Если `COleDateTime` объект имеет статус NULL, диапазон будет удален. Если `CTime` указатель или `COleDateTime` указатель NULL, диапазон будет удален.

### <a name="example"></a>Пример

  Смотрите пример [для CDateTimeCtrl::GetRange](#getrange).

## <a name="cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl:SetTime

Устанавливает время в контроле сборщика даты и времени.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>Параметры

*времяНовые*<br/>
Ссылка на объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий элемент, на который будет установлен элемент управления.

*pTimeNew*<br/>
Во второй версии выше указатель на объект [CTime,](../../atl-mfc-shared/reference/ctime-class.md) содержащий время, к которому будет установлен элемент управления. В третьей версии выше указатель на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) содержащую время, к которому будет установлен элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [DTM_SETSYSTEMTIME,](/windows/win32/Controls/dtm-setsystemtime)как описано в SDK Windows. `SetTime`В реализации MFC, вы `COleDateTime` можете `CTime` использовать или классов, `SYSTEMTIME` или вы можете использовать структуру, чтобы установить информацию о времени.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)
