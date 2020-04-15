---
title: Класс CTime
ms.date: 10/18/2018
f1_keywords:
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
ms.openlocfilehash: e6e471fe648c5fa370cce750e8569e158eb1ffe4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317568"
---
# <a name="ctime-class"></a>Класс CTime

Представляет собой абсолютное время и дату.

## <a name="syntax"></a>Синтаксис

```
class CTime
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTime::CTime](#ctime)|Строит `CTime` объекты различными способами.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTime::Формат](#format)|Преобразует `CTime` объект в отформатированную строку, основанную на локальном часовом поясе.|
|[CTime::FormatGmt](#formatgmt)|Преобразует `CTime` объект в отформатированную строку, основанную на UTC.|
|[Ctime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Преобразует информацию о времени, хранящуюся в `CTime` объекте, в структуру DBTIMESTAMP, совместимую с Win32.|
|[CTime::GetAsSystemTime](#getassystemtime)|Преобразует информацию о времени, хранящуюся в `CTime` объекте, в структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) совместимую с Win32.|
|[CTime::GetCurrentTime](#getcurrenttime)|Создает `CTime` объект, представляющий текущее время (функция статического члена).|
|[CTime::GetDay](#getday)|Возвращает день, представляющий `CTime` объект.|
|[Ctime::GetDayOfWeek](#getdayofweek)|Возвращает день недели, представленный `CTime` объектом.|
|[Ctime::GetGmtTm](#getgmttm)|Разбивание `CTime` объекта на компоненты на основе UTC.|
|[CTime::GetHour](#gethour)|Возвращает час, представленный `CTime` объектом.|
|[CTime::GetLocalTm](#getlocaltm)|Разбивка объекта на `CTime` компоненты на основе локального часового пояса.|
|[CTime::GetMinute](#getminute)|Возвращает минуту, представленную объектом. `CTime`|
|[CTime::GetMonth](#getmonth)|Возвращает месяц, представленный `CTime` объектом.|
|[CTime::GetSecond](#getsecond)|Возвращает второй представленный `CTime` объектом.|
|[CTime::GetTime](#gettime)|Возвращает **__time64_t** значение для `CTime` данного объекта.|
|[CTime::GetYear](#getyear)|Возвращает год, представленный `CTime` объектом.|
|[CTime::Serialize64](#serialize64)|Сериализирует данные в архив или из нее.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор - -](#operator_add_-)|Эти операторы добавляют `CTimeSpan` `CTime` и вычитают и объекты.|
|[оператором, --](#operator_add_eq_-_eq)|Эти операторы добавляют `CTimeSpan` и вычитают `CTime` объект к этому объекту и из них.|
|[Оператор](#operator_eq)|Оператор назначения.|
|[оператор, < и т.д.](#ctime_comparison_operators)|Операторы сравнения.|

## <a name="remarks"></a>Remarks

`CTime`не имеет базового класса.

`CTime`значения основаны на скоординированном универсальном времени (UTC), что эквивалентно скоординированному универсальному времени (Greenwich Mean Time, GMT). [Узнайте](../../c-runtime-library/time-management.md) о том, как определяется часовой пояс, ознакомьтесь с информацией о временном поясе.

При создании `CTime` объекта установите `nDST` параметр до 0, чтобы указать, что стандартное время действует, или на значение, превышающее 0, чтобы указать, что время летнего времени действует, или к значению менее нуля, чтобы иметь код библиотеки c run-time, вычислить, действует ли стандартное время или летнее время. `tm_isdst` — это обязательное поле. Если не установить, его значение не определено и значение возврата от [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) непредсказуемо. Если `timeptr` указывает на структуру тм, возвращенную предыдущим вызовом `tm_isdst` [asctime_s,](../../c-runtime-library/reference/asctime-s-wasctime-s.md) [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)или [localtime_s,](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)поле содержит правильное значение.

Класс компаньона, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), представляет собой временной интервал.

И `CTime` `CTimeSpan` классы не предназначены для произвобовательных. Поскольку виртуальных функций нет, `CTimeSpan` размер объектов `CTime` составляет ровно 8 байтов. Большинство функций членов являются внеочередными.

> [!NOTE]
> Верхний предел даты 12/31/3000. Нижний предел 1/1/1970 12:00 AM GMT.

Для получения дополнительной `CTime`информации об использовании, [Time Management](../../c-runtime-library/time-management.md) [см.](../../atl-mfc-shared/date-and-time.md)

> [!NOTE]
> Структура `CTime` изменена с МФЦ 7.1 на MFC 8.0. Если вы сериализируете структуру `CTime` с помощью оператора ** <<** по MFC 8.0 или более поздней версии, полученный файл не будет читаемым на старых версиях MFC.

## <a name="requirements"></a>Требования

**Заголовок:** atltime.h

## <a name="ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a>Операторы сравнения CTime

Операторы сравнения.

```
bool operator==(CTime time) const throw();
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw();
```

### <a name="parameters"></a>Параметры

*time*<br/>
Сравниваемый объект `CTime`.

### <a name="return-value"></a>Возвращаемое значение

Эти операторы сравнить два абсолютных раз и вернуться правда, если условие верно; в противном случае FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

## <a name="ctimectime"></a><a name="ctime"></a>CTime::CTime

Создает новый `CTime` объект, инициализированный с указанным временем.

```
CTime() throw();
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts, int nDST = -1) throw();
```

### <a name="parameters"></a>Параметры

*timeSrc*<br/>
Указывает `CTime` объект, который уже существует.

*time*<br/>
Значение `__time64_t` времени, которое является числом секунд после 1 января 1970 UTC. Обратите внимание, что это будет скорректировано в вашем местном времени. Например, если вы находитесь в `CTime` Нью-йорке и создаете объект, пройдя параметр 0, [CTime::GetMonth](#getmonth) вернет 12.

*nГод*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Указывает значения даты и времени, которые должны `CTime` быть скопированы в новый объект.

*nDST*<br/>
Указывает, действует ли летнее время. Может иметь одно из трех значений:

- *nDST* установлен на 0Стандартное время действует.

- *nDST* установлен на значение больше, чем 0Daylight экономии время в силе.

- *nDST* установлен на значение менее 0По умолчанию. Автоматически вычисляет ли стандартное время или летнее время в силе.

*wDosDate*, *wDosTime*<br/>
Значения даты и времени MS-DOS должны быть преобразованы в значение `CTime` даты/времени и скопированы в новый объект.

*St*<br/>
Структура [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) которая должна быть преобразована в значение `CTime` даты/времени и скопирована в новый объект.

*Метрах*<br/>
Структура [FILETIME,](/windows/win32/api/minwinbase/ns-minwinbase-filetime) которая должна быть преобразована в значение `CTime` даты/времени и скопирована в новый объект.

*dbts*<br/>
Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.

### <a name="remarks"></a>Remarks

Каждый конструктор описан ниже:

- `CTime();`Строит неначальный `CTime` объект. Этот конструктор позволяет определить `CTime` массивы объектов. Вы должны инициализировать такие массивы с действительными временами перед использованием.

- `CTime( const CTime& );`Строит `CTime` объект из `CTime` другого значения.

- `CTime( __time64_t );`Строит `CTime` объект из **__time64_t** типа. Этот конструктор ожидает время UTC и преобразует результат в локальное время перед хранением результата.

- `CTime( int, int, ...);`Строит `CTime` объект из компонентов локального времени с каждым компонентом, ограниченным на следующие диапазоны:

   |Компонент|Диапазон|
   |---------------|-----------|
   |*nГод*|1970-3000|
   |*nМесяц*|1–12|
   |*nДень*|1–31|
   |*nЧас*|0-23|
   |*nMin*|0-59|
   |*nSec*|0-59|

   Этот конструктор делает соответствующее преобразование в UTC. Версия Debug библиотеки класса Microsoft Foundation утверждает, что один или несколько компонентов времени находятся вне диапазона. Перед вызовом необходимо проверить аргументы. Этот конструктор ожидает местного времени.

- `CTime( WORD, WORD );`Строит `CTime` объект из указанной даты ms-DOS и временных значений. Этот конструктор ожидает местного времени.

- `CTime( const SYSTEMTIME& );`Строит `CTime` объект из `SYSTEMTIME` структуры. Этот конструктор ожидает местного времени.

- `CTime( const FILETIME& );`Строит `CTime` объект из `FILETIME` структуры. Скорее всего, `CTime FILETIME` вы не будете использовать инициализацию напрямую. Если вы `CFile` используете объект для `CFile::GetStatus` управления файлом, извлекает штамп `CTime` времени файла `FILETIME` для вас через объект, инициализированный со структурой. Этот конструктор берет на себя время, основанное на UTC, и автоматически преобразует значение в локальное время перед хранением результата.

   > [!NOTE]
   > Конструктор, использующий `DBTIMESTAMP` параметр, доступен только при включении OLEDB.h.

Для получения дополнительной информации [см. SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) и [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) структуры в Windows SDK. Также смотрите [MS-DOS Дата и время](/windows/win32/SysInfo/ms-dos-date-and-time) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

## <a name="ctimeformat"></a><a name="format"></a>CTime::Формат

Вызовите эту функцию участника, чтобы создать отформатированный представление значения времени даты.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Строка форматирования, `printf` похожая на строку форматирования. Коды форматирования, предшествующий знаку процента`%` `CTime` () заменяются соответствующим компонентом. Другие символы строки форматирования копируются без изменений в возвращенную строку. Ознакомьтесь с функцией run-time [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) для списка кодов форматирования.

*nФорматид*<br/>
Идентификатор строки, идентифицирует этот формат.

### <a name="return-value"></a>Возвращаемое значение

[CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий отформатированные время.

### <a name="remarks"></a>Remarks

Если состояние этого `CTime` объекта является нулевым, значение возврата является пустой строкой.

Этот метод выбрасывает исключение, если значение времени даты для формата не колеблется от полуночи, 1 января 1970 года по 31 декабря 3000 Всеобщее координированное время (UTC).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

## <a name="ctimeformatgmt"></a><a name="formatgmt"></a>CTime::FormatGmt

Генерирует отформатированную строку, `CTime` соответствующую этому объекту.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Определяет строку форматирования, похожую `printf` на строку форматирования. Подробнее о функциях run-time [strftime.](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)

*nФорматид*<br/>
Идентификатор строки, идентифицирует этот формат.

### <a name="return-value"></a>Возвращаемое значение

[CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий отформатированные время.

### <a name="remarks"></a>Remarks

Значение времени не преобразуется и, таким образом, отражает UTC.

Этот метод выбрасывает исключение, если значение времени даты для формата не колеблется от полуночи, 1 января 1970 года по 31 декабря 3000 Всеобщее координированное время (UTC).

### <a name="example"></a>Пример

Смотрите пример [Для CTime::Формат](#format).

## <a name="ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>Ctime::GetAsDBTIMESTAMP

Вызовите эту функцию участника для `CTime` преобразования временной информации, хранящейся в объекте, в структуру DBTIMESTAMP, совместимую с Win32.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Параметры

*dbts*<br/>
Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Хранит полученное время в референтной структуре *dbts.* Структура `DBTIMESTAMP` данных, инициализированная этой `fraction` функцией, будет сведена к нулю.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

## <a name="ctimegetassystemtime"></a><a name="getassystemtime"></a>CTime::GetAsSystemTime

Вызовите эту функцию участника, `CTime` чтобы преобразовать информацию о времени, хранящуюся в объекте, в структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) совместимую с Win32.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Параметры

*timeDest*<br/>
Ссылка на структуру [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) которая будет удерживать `CTime` преобразованное значение даты/времени объекта.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

`GetAsSystemTime`хранит полученное время в референтной структуре *timeDest.* Структура `SYSTEMTIME` данных, инициализированная этой `wMilliseconds` функцией, будет сведена к нулю.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

## <a name="ctimegetcurrenttime"></a><a name="getcurrenttime"></a>CTime::GetCurrentTime

Возвращает `CTime` объект, представляющий текущее время.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Remarks

Возвращает текущую дату и время системы в скоординированное универсальное время (UTC).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

## <a name="ctimegetday"></a><a name="getday"></a>CTime::GetDay

Возвращает день, представляющий `CTime` объект.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает день месяца, в зависимости от местного времени, в диапазоне от 1 до 31.

### <a name="remarks"></a>Remarks

Эта функция `GetLocalTm`вызывает, который использует внутренний, статично выделенный буфер. Данные в этом буфере перезаписаны `CTime` из-за вызовов на другие функции членов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

## <a name="ctimegetdayofweek"></a><a name="getdayofweek"></a>Ctime::GetDayOfWeek

Возвращает день недели, представленный `CTime` объектом.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает день недели по местному времени; 1 - воскресенье, 2 - понедельник, до 7 - суббота.

### <a name="remarks"></a>Remarks

Эта функция `GetLocalTm`вызывает, который использует внутренний статично выделенный буфер. Данные в этом буфере перезаписаны `CTime` из-за вызовов на другие функции членов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

## <a name="ctimegetgmttm"></a><a name="getgmttm"></a>Ctime::GetGmtTm

Получает **структуру тм,** содержащий разложение `CTime` времени, содержащегося в этом объекте.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*Ptm*<br/>
Указывает на буфер, который будет получать данные о времени. Если этот указатель ЯВЛЯЕТСЯ NULL, выбрасывается исключение.

### <a name="return-value"></a>Возвращаемое значение

Указатель на заполненный **тм структуры,** как это определено в файле TIME. H. Смотрите [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) для макета структуры.

### <a name="remarks"></a>Remarks

`GetGmtTm`возвращает UTC.

*ptm* не может быть NULL. Если вы хотите вернуться к старому поведению, в котором *ptm* может быть NULL, чтобы указать, что внутренний, статично выделенный буфер должен быть использован, то неопределить _SECURE_ATL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

## <a name="ctimegethour"></a><a name="gethour"></a>CTime::GetHour

Возвращает час, представленный `CTime` объектом.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает час, основанный на местном времени, в диапазоне от 0 до 23.

### <a name="remarks"></a>Remarks

Эта функция `GetLocalTm`вызывает, который использует внутренний статично выделенный буфер. Данные в этом буфере перезаписаны `CTime` из-за вызовов на другие функции членов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

## <a name="ctimegetlocaltm"></a><a name="getlocaltm"></a>CTime::GetLocalTm

Получает **структуру тм,** содержащий разложение `CTime` времени, содержащегося в этом объекте.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*Ptm*<br/>
Указывает на буфер, который будет получать данные о времени. Если этот указатель ЯВЛЯЕТСЯ NULL, выбрасывается исключение.

### <a name="return-value"></a>Возвращаемое значение

Указатель на заполненный **тм структуры,** как это определено в файле TIME. H. Смотрите [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) для макета структуры.

### <a name="remarks"></a>Remarks

`GetLocalTm`возвращается по местному времени.

*ptm* не может быть NULL. Если вы хотите вернуться к старому поведению, в котором *ptm* может быть NULL, чтобы указать, что внутренний, статично выделенный буфер должен быть использован, то неопределить _SECURE_ATL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

## <a name="ctimegetminute"></a><a name="getminute"></a>CTime::GetMinute

Возвращает минуту, представленную объектом. `CTime`

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает минуту, основанную на местном времени, в диапазоне от 0 до 59.

### <a name="remarks"></a>Remarks

Эта функция `GetLocalTm`вызывает, который использует внутренний статично выделенный буфер. Данные в этом буфере перезаписаны `CTime` из-за вызовов на другие функции членов.

### <a name="example"></a>Пример

Смотрите пример [GetHour](#gethour).

## <a name="ctimegetmonth"></a><a name="getmonth"></a>CTime::GetMonth

Возвращает месяц, представленный `CTime` объектом.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает месяц, основанный на местном времени, в диапазоне от 1 до 12 (1 январь).

### <a name="remarks"></a>Remarks

Эта функция `GetLocalTm`вызывает, который использует внутренний статично выделенный буфер. Данные в этом буфере перезаписаны `CTime` из-за вызовов на другие функции членов.

### <a name="example"></a>Пример

Смотрите пример [GetDay](#getday).

## <a name="ctimegetsecond"></a><a name="getsecond"></a>CTime::GetSecond

Возвращает второй представленный `CTime` объектом.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает второй, основанный на местном времени, в диапазоне от 0 до 59.

### <a name="remarks"></a>Remarks

Эта функция `GetLocalTm`вызывает, который использует внутренний статично выделенный буфер. Данные в этом буфере перезаписаны `CTime` из-за вызовов на другие функции членов.

### <a name="example"></a>Пример

Смотрите пример [GetHour](#gethour).

## <a name="ctimegettime"></a><a name="gettime"></a>CTime::GetTime

Возвращает **__time64_t** значение для `CTime` данного объекта.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

`GetTime`возвращает количество секунд между текущим `CTime` объектом и 1 января 1970 года.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

## <a name="ctimegetyear"></a><a name="getyear"></a>CTime::GetYear

Возвращает год, представленный `CTime` объектом.

```
int GetYear();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает год, основанный на местном времени, в диапазоне 1 января 1970, до 18 января 2038 (включительно).

### <a name="remarks"></a>Remarks

Эта функция `GetLocalTm`вызывает, который использует внутренний статично выделенный буфер. Данные в этом буфере перезаписаны `CTime` из-за вызовов на другие функции членов.

### <a name="example"></a>Пример

Смотрите пример [GetDay](#getday).

## <a name="ctimeoperator-"></a><a name="operator_eq"></a>CTime::оператор

Оператор назначения.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Параметры

*time*<br/>
Новое значение даты/времени.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CTime` объект.

### <a name="remarks"></a>Remarks

Этот перегруженный оператор назначения копирует время `CTime` источника в этом объекте. Внутреннее временное `CTime` хранилище в объекте не зависит от часового пояса. Преобразование часового пояса не требуется во время назначения.

## <a name="ctimeoperator---"></a><a name="operator_add_-"></a>CTime::оператор, -

Эти операторы добавляют `CTimeSpan` `CTime` и вычитают и объекты.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Параметры

*Timespan*<br/>
Объект, `CTimeSpan` который должен быть добавлен или вычитан.

*time*<br/>
Объект, `CTime` который будет вычитан.

### <a name="return-value"></a>Возвращаемое значение

Объект `CTime` `CTimeSpan` или объект, представляющий результат операции.

### <a name="remarks"></a>Remarks

`CTime`объекты представляют `CTimeSpan` абсолютное время, объекты представляют относительное время. Первые два оператора позволяют добавлять `CTimeSpan` и вычитать объекты к объектам и из них. `CTime` Третий оператор позволяет вычесть `CTime` один объект из `CTimeSpan` другого, чтобы дать объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

## <a name="ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a>CTime::оператор, --

Эти операторы добавляют `CTimeSpan` и вычитают `CTime` объект к этому объекту и из них.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Объект, `CTimeSpan` который должен быть добавлен или вычитан.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CTime` объект.

### <a name="remarks"></a>Remarks

Эти операторы позволяют добавлять `CTimeSpan` и вычесть `CTime` объект и из этого объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

## <a name="ctimeserialize64"></a><a name="serialize64"></a>CTime::Serialize64

> [!NOTE]
> Этот метод доступен только в проектах MFC.

Сериализирует данные, связанные с переменной участника, в архив или из нее.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
Объект, `CArchive` который требуется обновить.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CArchive` объект.

## <a name="see-also"></a>См. также раздел

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
