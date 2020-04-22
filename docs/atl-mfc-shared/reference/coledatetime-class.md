---
title: Класс COleDateTime
ms.date: 03/27/2019
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
ms.openlocfilehash: 8ba09430427b6ece8ae5956912cbcc40fb33fcf2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747169"
---
# <a name="coledatetime-class"></a>Класс COleDateTime

Инкапсулирует тип `DATE` данных, который используется в автоматизации OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDateTime
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDateTime:: COleDateTime](#coledatetime)|Формирует объект `COleDateTime`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDateTime::Формат](#format)|Генерирует отформатированный строковый `COleDateTime` репрезентации объекта.|
|[Coledatetime::GetasDBTIMESTAMP](#getasdbtimestamp)|Вызовите этот метод, `COleDateTime` чтобы получить `DBTIMESTAMP` время в объекте в качестве структуры данных.|
|[ColedateTime:GetasSystemTime](#getassystemtime)|Вызовите этот метод, `COleDateTime` чтобы получить время в объекте в качестве структуры данных [SYSTEMTIME.](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)|
|[ColedateTime::GetasUDATE](#getasudate)|Вызовите этот метод, `COleDateTime` чтобы `UDATE` получить время в качестве структуры данных.|
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Создает `COleDateTime` объект, представляющий текущее время (функция статического члена).|
|[COleDateTime::GetDay](#getday)|Возвращает день, `COleDateTime` который представляет этот объект (1 - 31).|
|[COledateTime::GetDayofWeek](#getdayofweek)|Возвращает день недели, `COleDateTime` который представляет этот объект (воскресенье No 1).|
|[COledateTime::GetdayofYear](#getdayofyear)|Возвращает день года этот `COleDateTime` объект представляет (1 января и 1).|
|[COleDateTime::GetHour](#gethour)|Возвращает час, `COleDateTime` который представляет этот объект (0 - 23).|
|[COleDateTime:GetMinute](#getminute)|Возвращает минуту, что представляет этот `COleDateTime` объект (0 - 59).|
|[COleDateTime::GetMonth](#getmonth)|Возвращает месяц, `COleDateTime` который представляет этот объект (1 - 12).|
|[COleDateTime::GetSecond](#getsecond)|Возвращает второй `COleDateTime` объект представляет (0 - 59).|
|[COleDateTime:GetStatus](#getstatus)|Получает статус (действительность) `COleDateTime` этого объекта.|
|[COleDateTime::GetYear](#getyear)|Возвращает год, `COleDateTime` который представляет этот объект.|
|[COleDateTime::ParseDateTime](#parsedatetime)|Читает значение даты/времени из строки `COleDateTime`и устанавливает значение .|
|[COleDateTime::SetDate](#setdate)|Устанавливает значение этого `COleDateTime` объекта к указанному значению только для даты.|
|[COleDateTime::SetDate](#setdatetime)|Устанавливает значение этого `COleDateTime` объекта к указанной дате/времени.|
|[COleDateTime::SetStatus](#setstatus)|Устанавливает статус (действительность) `COleDateTime` этого объекта.|
|[COleDateTime::SetTime](#settime)|Устанавливает значение этого `COleDateTime` объекта к указанному значению только по времени.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[COleDateTime::оператор , COleDateTime::оператор < и т.д.](#coledatetime_relational_operators)|Сравните `COleDateTime` два значения.|
|[COleDateTime::оператор No, COleDateTime:Оператор -](#operator_add_-)|Добавить и `COleDateTime` вычесть значения.|
|[COleDateTime::оператор, COleDateTime::оператор -](#operator_add_eq_-_eq)|Добавить и `COleDateTime` вычесть `COleDateTime` значение из этого объекта.|
|[COleDateTime::оператор](#operator_eq)|Копирует `COleDateTime` значение.|
|[COleDateTime:оператор DATE, COleDateTime::оператор Дата](#operator_date)|Преобразует `COleDateTime` значение в `DATE` `DATE*`или .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleDateTime::m_dt](#m_dt)|Содержит базовый `DATE` для `COleDateTime` этого объекта.|
|[COleDateTime::m_status](#m_status)|Содержит статус этого `COleDateTime` объекта.|

## <a name="remarks"></a>Remarks

`COleDateTime`не имеет базового класса.

Это один из возможных типов для типа данных [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) автоматизации OLE. Значение `COleDateTime` представляет собой абсолютное значение даты и времени.

Тип `DATE` реализован как значение плавающей точки. Дни измеряются с 30 декабря 1899 года, в полночь. В следующей таблице показаны некоторые даты и связанные с ними значения:

|Дата|Значение|
|----------|-----------|
|29 декабря 1899, полночь|-1.0|
|29 декабря 1899 г., 6:00|-1.25|
|30 декабря 1899, полночь|0,0|
|31 декабря 1899, полночь|1.0|
|1 января 1900 г., 6:00|2.25|

> [!CAUTION]
> В таблице выше, хотя дневные значения становятся отрицательными до полуночи 30 декабря 1899 года, значения времени суток этого не делают. Например, 6:00 AM всегда представлено дробным значением 0,25 независимо от того, является ли цельный день положительным (после 30 декабря 1899 года) или отрицательным (до 30 декабря 1899 года). Это означает, что простое сравнение плавающей `COleDateTime` точки ошибочно сортирует представление 6:00 AM 12/29/1899 по **мере того,** как позднее, чем одно, представляющее 7:00 AM в тот же день.

Класс `COleDateTime` обрабатывает даты с 1 января 100, по 31 декабря 9999. Класс `COleDateTime` использует григорианский календарь; он не поддерживает даты Джулиана. `COleDateTime`игнорирует летнее время. [(См. Дату и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).)

> [!NOTE]
> Вы можете `%y` использовать формат для получения двухзначного года только для дат, начиная с 1900 года. Если вы `%y` используете формат на дату до 1900 года, код генерирует сбой ASSERT.

Этот тип также используется для представления значений только для дат или времени. По конвенции дата 0 (30 декабря 1899 г.) используется для значений только по времени, а время 00:00 (полночь) используется для значений только для дат.

Если вы `COleDateTime` создаете объект, используя дату менее 100, дата принимается, `GetDay` `GetHour`но `GetMinute`последующие звонки на `GetSecond` `GetYear`, `GetMonth`, , и неудачу и возвращение -1. Ранее можно было использовать двузначные даты, но даты должны быть на 100 или больше в MFC 4.2 и более поздних.

Чтобы избежать проблем, укажите четырехзначную дату. Пример:

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

Основные арифметические `COleDateTime` операции для значений используют сопутствующий класс [COleDateTimeSpan.](../../atl-mfc-shared/reference/coledatetimespan-class.md) `COleDateTimeSpan`значения определяют временной интервал. Отношения между этими классами аналогичны отношениям между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan.](../../atl-mfc-shared/reference/ctimespan-class.md)

Для получения дополнительной `COleDateTime` `COleDateTimeSpan` информации о [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)классах, см.

## <a name="requirements"></a>Требования

**Заголовок:** ATLComTime.h

## <a name="coledatetime-relational-operators"></a><a name="coledatetime_relational_operators"></a>COleDateTime Реляционные Операторы

Операторы сравнения.

```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```

### <a name="parameters"></a>Параметры

*date*<br/>
Сравниваемый объект `COleDateTime`.

### <a name="remarks"></a>Remarks

> [!NOTE]
> ATLASSERT будет происходить, если любой из двух действий является недействительным.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>Пример

Операторы **>=** ** \< **, **>**, **<** и, будет `COleDateTime` утверждать, если объект установлен на нулевую.

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

## <a name="coledatetimecoledatetime"></a><a name="coledatetime"></a>COleDateTime:: COleDateTime

Формирует объект `COleDateTime`.

```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& timeStamp) throw();
```

### <a name="parameters"></a>Параметры

*dateSrc*<br/>
Существующий `COleDateTime` объект, который должен `COleDateTime` быть скопирован в новый объект.

*varSrc*<br/>
Существующая `VARIANT` структура данных `COleVariant` (возможно, объект), которая должна быть преобразована в значение `COleDateTime` даты/времени (VT_DATE) и скопирована в новый объект.

*dtSrc*<br/>
Значение даты/времени`DATE`() для копирования `COleDateTime` в новый объект.

*timeSrc*<br/>
Значение `time_t` `__time64_t` или значение, необходимое для преобразования в значение `COleDateTime` даты/времени и скопировано в новый объект.

*systimeSrc*<br/>
Структура, `SYSTEMTIME` которая должна быть преобразована в значение даты/времени и скопирована в новый `COleDateTime` объект.

*filetimeSrc*<br/>
Структура, `FILETIME` которая должна быть преобразована в значение даты/времени и скопирована в новый `COleDateTime` объект. Используется `FILETIME` универсальное скоординированное время (UTC), так что если вы проходите местное время в структуре, ваши результаты будут неправильными. Для получения дополнительной информации смотрите [файлы Times](/windows/win32/SysInfo/file-times) в SDK Windows.

*nГод*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Укажите значения даты и времени, которые `COleDateTime` будут скопированы в новый объект.

*wDosDate*, *wDosTime*<br/>
Значения даты и времени MS-DOS должны быть преобразованы в значение `COleDateTime` даты/времени и скопированы в новый объект.

*Timestamp*<br/>
Ссылка на структуру [DBTimeStamp,](/dotnet/api/system.data.oledb.oledbtype) содержащую текущее местное время.

### <a name="remarks"></a>Remarks

Все эти конструкторы `COleDateTime` создают новые объекты, инициализированные к заданному значению. В следующей таблице показаны допустимые диапазоны для каждого компонента даты и времени:

|Компонент дата/время|Допустимый диапазон|
|--------------------------|-----------------|
|year|100 - 9999|
|month|0 - 12|
|day|0 - 31|
|hour|0 - 23|
|minute|0 - 59|
|second|0 - 59|

Обратите внимание, что фактическая верхняя граница дневного компонента варьируется в зависимости от компонентов месяца и года. Для получения подробной `SetDate` `SetDateTime` информации ознакомьтесь с функциями или функциями-членами.

Ниже приводится краткое описание каждого конструктора:

- `COleDateTime(`**)** Строит `COleDateTime` объект инициализированный до 0 (полночь, 30 декабря 1899).

- `COleDateTime(``dateSrc` **)** Строит `COleDateTime` объект из `COleDateTime` существующего объекта.

- `COleDateTime(`*varSrc* **)** строит `COleDateTime` объект. Попытки преобразовать структуру `VARIANT` или объект [COleVariant](../../mfc/reference/colevariant-class.md) в значение даты/времени () `VT_DATE` Если это преобразование успешно, преобразованное `COleDateTime` значение скопировано в новый объект. Если это не так, `COleDateTime` то значение объекта устанавливается до 0 (полночь, 30 декабря 1899) и его статус недействительным.

- `COleDateTime(``dtSrc` **)** Строит `COleDateTime` объект из `DATE` значения.

- `COleDateTime(``timeSrc` **)** Строит `COleDateTime` объект из `time_t` значения.

- `COleDateTime(`*systimeSrc* **)** строит `COleDateTime` объект `SYSTEMTIME` из значения.

- `COleDateTime(``filetimeSrc` **)** Строит `COleDateTime` объект из `FILETIME` значения. . Используется `FILETIME` универсальное скоординированное время (UTC), так что если вы проходите местное время в структуре, ваши результаты будут неправильными. Для получения дополнительной информации смотрите [Файл Таймс](/windows/win32/SysInfo/file-times) в Windows SDK.

- `COleDateTime(``nYear`, `nMonth` `nDay`, `nHour` `nMin`, `nSec` **, )** Строит `COleDateTime` объект из указанных численных значений.

- `COleDateTime(``wDosDate` `wDosTime` **, )** Строит `COleDateTime` объект из указанной даты MS-DOS и временных значений.

Для получения дополнительной `time_t` информации о [time](../../c-runtime-library/reference/time-time32-time64.md) типе *Run-Time Library Reference*данных см.

Для получения дополнительной информации смотрите структуры [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) и [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) в SDK Windows.

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

> [!NOTE]
> Конструктор, использующий `DBTIMESTAMP` параметр, доступен только при включении OLEDB.h.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

## <a name="coledatetimeformat"></a><a name="format"></a>COleDateTime::Формат

Создает отформатированный представление значения даты/времени.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Указывает один из следующих флагов местности:

- LOCALE_NOUSEROVERRIDE использовать настройки локального локального по умолчания системы вместо пользовательских настроек пользователя.

- VAR_TIMEVALUEONLY Игнорировать дату части во время разбора.

- VAR_DATEVALUEONLY Игнорировать временной части во время разбора.

*lcid*<br/>
Указывает идентификатор локализации для использования для преобразования. Для получения дополнительной информации [Language Identifiers](/windows/win32/Intl/language-identifiers)об идентификаторах языка см.

*lpszФормат*<br/>
Строка форматирования, `printf` похожая на строку форматирования. Каждый код форматирования, предшествующий знаку процента () `%`заменяется соответствующим `COleDateTime` компонентом. Другие символы строки форматирования копируются без изменений в возвращенную строку. Для получения дополнительной информации см. [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Значение и значение кодов форматирования `Format` для:

- `%H`Часы в текущем дне

- `%M`Минуты в текущем часе

- `%S`Секунды в текущей минуте

- `%%`Процент наяпийк

*nФорматид*<br/>
Идентификатор ресурса для строки управления форматом.

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий отформатированную дату/значение времени.

### <a name="remarks"></a>Remarks

Если состояние этого `COleDateTime` объекта является нулевым, значение возврата является пустой строкой. Если статус недействителен, строка возврата указывается ресурсом строки ATL_IDS_DATETIME_INVALID.

Краткое описание трех форм для этой функции следующим образом:

`Format`*(dwFlags,* *lcid)*<br/>
Эта форма форматирует значение, используя спецификации языка (локальные идентионные данные) для даты и времени. Используя параметры по умолчанию, эта форма будет печатать дату и время, если время часть 0 (полночь), и в этом случае он будет печатать только дату, или дата часть 0 (30 декабря 1899), и в этом случае он будет печатать только время. Если значение даты/времени 0 (30 декабря 1899 года, полночь), эта форма с параметрами по умолчанию будет печатать полночь.

`Format`( *lpszFormat*)<br/>
Эта форма форматирует значение с помощью строки формата, которая содержит специальные коды форматирования, которым предшествует знак процента (%), как в `printf`. Строка форматирования передается в качестве параметра функции. Для получения дополнительной информации о кодах форматирования см. [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в справке о Run-Time Library.

`Format`*(nFormatID*)<br/>
Эта форма форматирует значение с помощью строки формата, которая содержит специальные коды форматирования, которым предшествует знак процента (%), как в `printf`. Строка форматирования — это ресурс. Идентификатор этого ресурса строки передается как параметр. Для получения дополнительной информации о кодах форматирования см. [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в справке о *Библиотеке Run-Time*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

## <a name="coledatetimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>Coledatetime::GetasDBTIMESTAMP

Вызовите этот метод, `COleDateTime` чтобы получить `DBTIMESTAMP` время в объекте в качестве структуры данных.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>Параметры

*Timestamp*<br/>
Ссылка на структуру [DBTimeStamp.](/dotnet/api/system.data.oledb.oledbtype)

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Хранит полученное время в референтной структуре *timeStamp.* Структура `DBTIMESTAMP` данных, инициализированная этой `fraction` функцией, будет сведена к нулю.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

## <a name="coledatetimegetassystemtime"></a><a name="getassystemtime"></a>ColedateTime:GetasSystemTime

Вызовите этот метод, `COleDateTime` чтобы получить `SYSTEMTIME` время в объекте в качестве структуры данных.

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>Параметры

*sysTime*<br/>
Ссылка на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения преобразованного `COleDateTime` значения даты/времени от объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха; FALSE, если преобразование `COleDateTime` не удается, или если объект является недействительным или недействительным.

### <a name="remarks"></a>Remarks

`GetAsSystemTime`хранит полученное время в референтном объекте *sysTime.* Структура `SYSTEMTIME` данных, инициализированная этой `wMilliseconds` функцией, будет сведена к нулю.

Для получения дополнительной информации о `COleDateTime` состоянии информации, хранящемся в объекте, [см.](#getstatus)

## <a name="coledatetimegetasudate"></a><a name="getasudate"></a>ColedateTime::GetasUDATE

Вызовите этот метод, `COleDateTime` чтобы получить `UDATE` время в объекте в качестве структуры данных.

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>Параметры

*uDate*<br/>
Ссылка на `UDATE` структуру для получения преобразованного `COleDateTime` значения даты/времени от объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха; FALSE, если преобразование `COleDateTime` не удается, или если объект является недействительным или недействительным.

### <a name="remarks"></a>Remarks

Структура `UDATE` представляет собой "распакованный" дату.

## <a name="coledatetimegetcurrenttime"></a><a name="getcurrenttime"></a>COleDateTime::GetCurrentTime

Вызовите эту функцию статического члена, чтобы вернуть текущее значение даты/времени.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

## <a name="coledatetimegetday"></a><a name="getday"></a>COleDateTime::GetDay

Получает день месяца, представленный этой датой/значением времени.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

День месяца, представленный значением этого `COleDateTime` объекта `COleDateTime::error` или если день не может быть получен.

### <a name="remarks"></a>Remarks

Допустимые значения возврата колеблют от 1 до 31.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

## <a name="coledatetimegetdayofweek"></a><a name="getdayofweek"></a>COledateTime::GetDayofWeek

Получает день месяца, представленный этой датой/значением времени.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

День недели, представленный значением этого `COleDateTime` объекта `COleDateTime::error` или если день недели не может быть получен.

### <a name="remarks"></a>Remarks

Допустимые значения возврата варьируются от 1 до 7, где 1'Sunday, 2"понедельник, и так далее.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

## <a name="coledatetimegetdayofyear"></a><a name="getdayofyear"></a>COledateTime::GetdayofYear

Получает день года, представленный этой датой/значением времени.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

День года, представленный стоимостью этого `COleDateTime` объекта, или `COleDateTime::error` если день года не может быть получен.

### <a name="remarks"></a>Remarks

Допустимые значения возврата варьируются от 1 до 366, где 1 января и 1.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

## <a name="coledatetimegethour"></a><a name="gethour"></a>COleDateTime::GetHour

Получает час, представленный этой датой/значением времени.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Час, представленный значением `COleDateTime` этого `COleDateTime::error` объекта или если час не может быть получен.

### <a name="remarks"></a>Remarks

Допустимые значения возврата колеблют от 0 до 23.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

## <a name="coledatetimegetminute"></a><a name="getminute"></a>COleDateTime:GetMinute

Получает минуту, представленную этим значением даты/времени.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Минута, представленная значением `COleDateTime` этого `COleDateTime::error` объекта или если минута не может быть получена.

### <a name="remarks"></a>Remarks

Допустимые значения возврата колеблют от 0 до 59.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Пример

Смотрите пример [GetHour](#gethour).

## <a name="coledatetimegetmonth"></a><a name="getmonth"></a>COleDateTime::GetMonth

Получает месяц, представленный этой датой/значением времени.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Месяц, представленный значением `COleDateTime` этого `COleDateTime::error` объекта или если месяц не может быть получен.

### <a name="remarks"></a>Remarks

Допустимые значения возврата колеблют от 1 до 12.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [Getday](#getday)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Пример

Смотрите пример [GetDay](#getday).

## <a name="coledatetimegetsecond"></a><a name="getsecond"></a>COleDateTime::GetSecond

Получает второе, представленное этой датой/значением времени.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Второй представлен значением этого `COleDateTime` объекта `COleDateTime::error` или, если второй не может быть получен.

### <a name="remarks"></a>Remarks

Допустимые значения возврата колеблют от 0 до 59.

> [!NOTE]
> Класс `COleDateTime` не поддерживает високосные секунды.

Для получения дополнительной информации о [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)реализации , `COleDateTime`см.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Пример

Смотрите пример [GetHour](#gethour).

## <a name="coledatetimegetstatus"></a><a name="getstatus"></a>COleDateTime:GetStatus

Получает статус (действительность) данного `COleDateTime` объекта.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает статус этого `COleDateTime` значения. Если вы `GetStatus` призываете объект, построенный `COleDateTime` по умолчанию, он вернется действительным. Если вы `GetStatus` призываете `COleDateTime` объект, инициализированный `GetStatus` с набором конструктора, сытным в ней, вернетнулнулнул.

### <a name="remarks"></a>Remarks

Значение возврата определяется `DateTimeStatus` перечисленным типом, который определяется `COleDateTime` в классе.

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

Краткое описание этих значений статуса см.

- `COleDateTime::error`Указывается, что ошибка произошла при попытке получить часть значения даты/времени.

- `COleDateTime::valid`Означает, `COleDateTime` что этот объект является действительным.

- `COleDateTime::invalid`Указывает, `COleDateTime` что этот объект является недействительным; то есть, его значение может быть неправильным.

- `COleDateTime::null`Означает, `COleDateTime` что этот объект является нулевым, т.е. что для этого объекта не было поставлено значение. (Это "нулевой" в базе данных смысле "не имеет значения", в отличие от СЗ NULL.)

Статус `COleDateTime` объекта является недействительным в следующих случаях:

- Если его значение устанавливается из `VARIANT` значения или `COleVariant` значения, которое не может быть преобразовано в значение даты/времени.

- Если его значение устанавливается `SYSTEMTIME`из `FILETIME` `time_t`значения, или значения, которое не может быть преобразовано в допустимую дату/значение времени.

- Если его значение `SetDateTime` устанавливается недействительными значениями параметров.

- Если этот объект испытал переполнение или недопоге во время `+=` `-=`операции арифметического назначения, а именно.

- Если недействительное значение было назначено этому объекту.

- Если статус этого объекта был явно установлен `SetStatus`на недействительное использование .

Для получения дополнительной информации об операциях, которые могут привести статус к инвалидности, см.

- [Coledatetime](#coledatetime)

- [SetDateTime](#setdatetime)

- [оператор No, -](#operator_add_-)

- [оператором, --](#operator_add_eq_-_eq)

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

## <a name="coledatetimegetyear"></a><a name="getyear"></a>COleDateTime::GetYear

Получает год, представленный этой датой/значением времени.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Год, представленный стоимостью `COleDateTime` этого `COleDateTime::error` объекта или если год не может быть получен.

### <a name="remarks"></a>Remarks

Допустимые значения возврата варьируются от 100 до 9999, что включает в себя столетие.

Для получения информации о других функциях-членах, которые задавили значение этого `COleDateTime` объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

### <a name="example"></a>Пример

Смотрите пример [GetDay](#getday).

## <a name="coledatetimem_dt"></a><a name="m_dt"></a>COleDateTime::m_dt

Базовая `DATE` структура для `COleDateTime` этого объекта.

```
DATE m_dt;
```

### <a name="remarks"></a>Remarks

> [!CAUTION]
> Изменение значения объекта, доступ к `DATE` нему указателем, возвращенному этой `COleDateTime` функцией, изменит значение этого объекта. Статус этого `COleDateTime` объекта не изменяется.

Для получения дополнительной информации `DATE` о реализации [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)объекта см.

## <a name="coledatetimem_status"></a><a name="m_status"></a>COleDateTime::m_status

Содержит статус этого `COleDateTime` объекта.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>Remarks

Тип этого члена данных является перечисленным `DateTimeStatus`типом, который `COleDateTime` определяется в классе. Для получения дополнительной [информации, см. COleDateTime::GetStatus](#getstatus).

> [!CAUTION]
> Этот член данных предназначен для передовых ситуаций программирования. Вы должны использовать внеочередные функции членов [GetStatus](#getstatus) и [SetStatus.](#setstatus) Дополнительные предостережения читайте `SetStatus` в вопросе о явном настройке этого участника данных.

## <a name="coledatetimeoperator-"></a><a name="operator_eq"></a>COleDateTime::оператор

Копирует `COleDateTime` значение.

```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& uDate) throw();
```

### <a name="remarks"></a>Remarks

Эти операторы перегруженных назначений копируют значение `COleDateTime` исходной даты/времени в этом объекте. Краткое описание каждого из этих перегруженных операторов назначения следующим образом:

- **оператор No (** `dateSrc` **)** Значение и статус операнд скопированы `COleDateTime` в этот объект.

- **оператор No** *(varSrc* **)** Если преобразование значения [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) (или объекта [COleVariant)](../../mfc/reference/colevariant-class.md) в дату/время (VT_DATE) успешно, `COleDateTime` преобразованное значение скопировано в этот объект и его статус установлен в действии. Если преобразование не является успешным, значение этого объекта устанавливается до нуля (30 декабря 1899 года, полночь) и его статус недействительным.

- **оператор No (** `dtSrc` **)** Значение `DATE` скопировано `COleDateTime` в этот объект и его статус установлен в действии.

- **оператор No (** `timeSrc` **)** Значение `time_t` `__time64_t` или значение преобразуется и `COleDateTime` копируется в этот объект. Если преобразование успешно, статус этого объекта установлен в действии; в случае неудачи, он установлен недействительным.

- **оператор** *(systimeSrc* **)** Значение [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) преобразуется и копируется в этот `COleDateTime` объект. Если преобразование успешно, статус этого объекта установлен в действии; в случае неудачи, он установлен недействительным.

- **оператор No (** `uDate` **)** Значение `UDATE` преобразуется и копируется в этот `COleDateTime` объект. Если преобразование успешно, статус этого объекта установлен в действии; в случае неудачи, он установлен недействительным. Структура `UDATE` представляет собой "распакованный" дату. Для получения дополнительной информации см. [VarDateFromUdate](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate)

- **оператор No (** `filetimeSrc` **)** Значение [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) преобразуется и копируется в этот `COleDateTime` объект. Если преобразование успешно, статус этого объекта установлен в действии; в противном случае он установлен недействительным. `FILETIME`использует универсальное координированное время (UTC), так что если вы проходите время UTC в структуре, ваши результаты будут преобразованы из UTC время по местному времени, и будет храниться в качестве варианта времени. Такое же поведение, как и в Visual C'6.0 и Visual C'.NET 2003 SP2. Для получения дополнительной информации смотрите [Файл Таймс](/windows/win32/SysInfo/file-times) в Windows SDK.

Для получения дополнительной информации смотрите запись [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) в Windows SDK.

Для получения дополнительной `time_t` информации о [time](../../c-runtime-library/reference/time-time32-time64.md) типе *Run-Time Library Reference*данных см.

Для получения дополнительной информации смотрите структуры [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) и [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) в SDK Windows.

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

## <a name="coledatetimeoperator---"></a><a name="operator_add_-"></a>COleDateTime::оператор No, -

Добавить и `ColeDateTime` вычесть значения.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>Remarks

`COleDateTime`объекты представляют собой абсолютное время. [Объекты COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) представляют относительное время. Первые два оператора позволяют добавлять `COleDateTimeSpan` и вычесть значение из `COleDateTime` значения. Третий оператор позволяет вычесть `COleDateTime` одно значение из `COleDateTimeSpan` другого, чтобы принести значение.

Если какая-либо из действий является нулевой, `COleDateTime` статус полученного значения является нулевым.

Если полученное `COleDateTime` значение выпадает за рамки приемлемых `COleDateTime` значений, статус этого значения является недействительным.

Если какая-либо из действий недействительна, а другая не `COleDateTime` является нулевой, статус полученного значения является недействительным.

**+** Операторы **-** и операторы `COleDateTime` будут утверждать, если объект установлен на нулевую. Например, примером можно ознакомиться с [примером к релямным операторам COleDate.](#coledatetime_relational_operators)

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

## <a name="coledatetimeoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTime::Оператор, --

Добавить и `ColeDateTime` вычесть `COleDateTime` значение из этого объекта.

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Remarks

Эти операторы позволяют добавлять `COleDateTimeSpan` и вычесть `COleDateTime`значение и из этого. Если какая-либо из действий является нулевой, `COleDateTime` статус полученного значения является нулевым.

Если полученное `COleDateTime` значение выпадает за пределы допустимых `COleDateTime` значений, статус этого значения устанавливается недействительным.

Если какая-либо из действий недействительна, а другая `COleDateTime` не является нулевой, статус полученного значения является недействительным.

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

**+=** Операторы **-=** и операторы `COleDateTime` будут утверждать, если объект установлен на нулевую. Например, примером можно ознакомиться с [примером к релямным операторам COleDate.](#coledatetime_relational_operators)

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

## <a name="coledatetimeoperator-date"></a><a name="operator_date"></a>COleDateTime::оператор DATE

Преобразует `ColeDateTime` значение в `DATE`.

```
operator DATE() const throw();
```

### <a name="remarks"></a>Remarks

Этот оператор `DATE` возвращает объект, значение которого скопировано с этого `COleDateTime` объекта. Для получения дополнительной информации `DATE` о реализации [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)объекта см.

Оператор `DATE` будет утверждать, `COleDateTime` если объект установлен на нулевую. Например, примером можно ознакомиться с [примером к релямным операторам COleDate.](#coledatetime_relational_operators)

## <a name="coledatetimeparsedatetime"></a><a name="parsedatetime"></a>COleDateTime::ParseDateTime

Сравнивает строку для чтения значения даты/времени.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>Параметры

*lpszDate*<br/>
Указатель на нулевую строку, которая должна быть разогнана. Дополнительные сведения см. в разделе "Заметки".

*dwFlags*<br/>
Отосевание флагов для настроек и разбора. Один или несколько из следующих флагов:

- LOCALE_NOUSEROVERRIDE использовать настройки локального локального по умолчания системы, а не пользовательские настройки пользователя.

- VAR_TIMEVALUEONLY Игнорировать дату части во время разбора.

- VAR_DATEVALUEONLY Игнорировать временной части во время разбора.

*lcid*<br/>
Указывает идентификатор локализации для использования для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если строка была успешно преобразована в значение даты/времени, в противном случае FALSE.

### <a name="remarks"></a>Remarks

Если строка была успешно преобразована в значение даты/времени, значение этого `COleDateTime` объекта устанавливается к этому значению, а его статус действителен.

> [!NOTE]
> Значения года должны лежать между 100 и 9999, включительно.

Параметр *lpszDate* может принимать различные форматы. Например, следующие строки содержат приемлемые форматы даты/времени:

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

Идентификатор локализации также повлияет на то, является ли формат строки приемлемым для преобразования в значение даты/времени.

В случае VAR_DATEVALUEONLY значение времени устанавливается в 0 или полночь. В случае VAR_TIMEVALUEONLY значение даты устанавливается на дату 0, т.е. 30 декабря 1899 года.

Если строка не может быть преобразована в значение даты/времени или если произошел `COleDateTime` численный переполнение, статус этого объекта является недействительным.

Для получения дополнительной информации о `COleDateTime` границах и [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)реализации значений, см.

## <a name="coledatetimesetdate"></a><a name="setdate"></a>COleDateTime::SetDate

Устанавливается дата `COleDateTime` этого объекта.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>Параметры

*nГод*, *nMonth*, *nDay*<br/>
Укажите компоненты даты, которые `COleDateTime` будут скопированы в этот объект.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если `COleDateTime` значение этого объекта было установлено успешно; в противном случае, 1. Это значение возврата основано на перечисленном типе. `DateTimeStatus` Для получения дополнительной [информации](#setstatus) см.

### <a name="remarks"></a>Remarks

Дата устанавливается для указанных значений. Время установлено на время 0, полночь.

Смотрите следующую таблицу для значений параметра:

|Параметр|Bounds|
|---------------|------------|
|*nГод*|100 - 9999|
|*nМесяц*|1 - 12|
|*nДень*|0 - 31|

Если день месяца переполнен, он преобразуется в правильный день следующего месяца и месяц и / или год приравливается соответственно. Дневное значение нуля указывает на последний день предыдущего месяца. Поведение такое же, как `SystemTimeToVariantTime`.

Если значение даты, указанное параметрами, не действительно, статус `COleDateTime::invalid`этого объекта устанавливается. Вы должны использовать [GetStatus](#getstatus) для проверки достоверности `DATE` значения и не должны предполагать, что значение [m_dt](#m_dt) останется неизменным.

Вот несколько примеров значений дат:

|*nГод*|*nМесяц*|*nДень*|Значение|
|-------------|--------------|------------|-----------|
|2000|2|29|29 февраля 2000 года|
|1776|7|4|4 июля 1776 г.|
|1925|4|35|35 апреля 1925 (недействительная дата)|
|10000|1|1|1 января 10000 (недействительная дата)|

Чтобы установить дату и время, [см. COleDateTime::SetDateTime](#setdatetime).

Для получения информации о функциях `COleDateTime` членов, которые задавивают вопрос о значении этого объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

## <a name="coledatetimesetdatetime"></a><a name="setdatetime"></a>COleDateTime::SetDate

Устанавливает дату и время `COleDateTime` этого объекта.

```
int SetDateTime(
    int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Параметры

*nГод*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Укажите компоненты даты и времени, `COleDateTime` которые будут скопированы в этот объект.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если `COleDateTime` значение этого объекта было установлено успешно; в противном случае, 1. Это значение возврата основано на перечисленном типе. `DateTimeStatus` Для получения дополнительной [информации](#setstatus) см.

### <a name="remarks"></a>Remarks

Смотрите следующую таблицу для значений параметра:

|Параметр|Bounds|
|---------------|------------|
|*nГод*|100 - 9999|
|*nМесяц*|1 - 12|
|*nДень*|0 - 31|
|*nЧас*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Если день месяца переполнен, он преобразуется в правильный день следующего месяца и месяц и / или год приравливается соответственно. Дневное значение нуля указывает на последний день предыдущего месяца. Поведение такое же, как [SystemTimeToVariantTime](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime).

Если значение даты или времени, указанное параметрами, не действительно, статус этого объекта устанавливается недействительным, а значение этого объекта не изменяется.

Вот несколько примеров значений времени:

|*nЧас*|*nMin*|*nSec*|Значение|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Недопустимо|
|9|60|0|Недопустимо|

Вот несколько примеров значений дат:

|*nГод*|*nМесяц*|*nДень*|Значение|
|-------------|--------------|------------|-----------|
|1995|4|15|15 апреля 1995 года|
|1789|7|14|17 июля 1789 г.|
|1925|2|30|Недопустимо|
|10000|1|1|Недопустимо|

Чтобы установить только дату, [см. COleDateTime::SetDate](#setdate). Чтобы установить только время, [см. COleDateTime::SetTime](#settime).

Для получения информации о функциях `COleDateTime` членов, которые задавивают вопрос о значении этого объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

### <a name="example"></a>Пример

Смотрите пример [GetStatus](#getstatus).

## <a name="coledatetimesetstatus"></a><a name="setstatus"></a>COleDateTime::SetStatus

Устанавливает состояние этого `COleDateTime` объекта.

```cpp
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>Параметры

*status*<br/>
Новое значение статуса `COleDateTime` для этого объекта.

### <a name="remarks"></a>Remarks

Значение параметра *состояния* определяется `DateTimeStatus` перечисленным типом, который `COleDateTime` определяется в классе. Подробнее о том, как получить информацию, читайте [в материале COleDateTime::GetStatus.](#getstatus)

> [!CAUTION]
> Эта функция предназначена для передовых ситуаций программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он будет использоваться для установки статуса **недействительным** или **недействительным.** Оператор назначения[(оператор )](#operator_eq)и [SetDateTime](#setdatetime) устанавливают состояние объекта на основе исходного значения (ы).

### <a name="example"></a>Пример

Смотрите пример [GetStatus](#getstatus).

## <a name="coledatetimesettime"></a><a name="settime"></a>COleDateTime::SetTime

Устанавливает время этого `COleDateTime` объекта.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Параметры

*nHour*, *nMin*, *nSec*<br/>
Укажите компоненты времени, которые `COleDateTime` будут скопированы в этот объект.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если `COleDateTime` значение этого объекта было установлено успешно; в противном случае, 1. Это значение возврата основано на перечисленном типе. `DateTimeStatus` Для получения дополнительной [информации](#setstatus) см.

### <a name="remarks"></a>Remarks

Время устанавливается для указанных значений. Дата установлена на дату 0, то есть 30 декабря 1899 года.

Смотрите следующую таблицу для значений параметра:

|Параметр|Bounds|
|---------------|------------|
|*nЧас*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Если значение времени, указанное параметрами, не действительно, статус этого объекта устанавливается недействительным, а значение этого объекта не изменяется.

Вот несколько примеров значений времени:

|*nЧас*|*nMin*|*nSec*|Значение|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Недопустимо|
|9|60|0|Недопустимо|

Чтобы установить дату и время, [см. COleDateTime::SetDateTime](#setdatetime).

Для получения информации о функциях `COleDateTime` членов, которые задавивают вопрос о значении этого объекта, см.

- [Getday](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Для получения дополнительной информации `COleDateTime` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

### <a name="example"></a>Пример

Смотрите пример [SetDate](#setdate).

## <a name="see-also"></a>См. также раздел

[Класс COleVariant](../../mfc/reference/colevariant-class.md)<br/>
[Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
