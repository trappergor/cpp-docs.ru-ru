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
ms.openlocfilehash: a1d62cca42e3110974b07dae143bafcf807fed7e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440490"
---
# <a name="ctime-class"></a>Класс CTime

Представляет абсолютное время и дату.

## <a name="syntax"></a>Синтаксис

```
class CTime
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CTime:: CTime](#ctime)|Конструирование `CTime` объектов различными способами.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CTime:: Format](#format)|Преобразует `CTime` объект в отформатированную строку, основываясь на местном часовом поясе.|
|[CTime:: Форматгмт](#formatgmt)|Преобразует `CTime` объект в отформатированную строку, основываясь на времени в формате UTC.|
|[CTime:: Жетасдбтиместамп](#getasdbtimestamp)|Преобразует сведения о времени, хранящиеся в объекте `CTime`, в структуру DBTIMESTAMP, совместимую с Win32.|
|[CTime:: Жетассистемтиме](#getassystemtime)|Преобразует сведения о времени, хранящиеся в объекте `CTime`, в структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , совместимую с Win32.|
|[CTime:: Жеткурренттиме](#getcurrenttime)|Создает объект `CTime`, представляющий текущее время (статическую функцию-член).|
|[CTime:: GetDay](#getday)|Возвращает день, представленный объектом `CTime`.|
|[CTime:: Жетдайофвик](#getdayofweek)|Возвращает день недели, представленный объектом `CTime`.|
|[CTime:: Жетгмттм](#getgmttm)|Разбивает `CTime` объект на компоненты, основываясь на времени в формате UTC.|
|[CTime:: в час](#gethour)|Возвращает час, представленный объектом `CTime`.|
|[CTime:: Жетлокалтм](#getlocaltm)|Разбивает `CTime` объект на компоненты — в зависимости от местного часового пояса.|
|[CTime:: Minute](#getminute)|Возвращает минуты, представленную объектом `CTime`.|
|[CTime:: в месяц](#getmonth)|Возвращает месяц, представленный объектом `CTime`.|
|[CTime:: в секунду](#getsecond)|Возвращает второй объект, представленный объектом `CTime`.|
|[CTime:: во время](#gettime)|Возвращает **__time64_t** значение для данного объекта `CTime`.|
|[CTime:: в г.](#getyear)|Возвращает год, представленный объектом `CTime`.|
|[CTime:: Serialize64](#serialize64)|Сериализует данные в архив или из него.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator +-](#operator_add_-)|Эти операторы добавляют и вычитают `CTimeSpan` и `CTime` объекты.|
|[operator + =,-=](#operator_add_eq_-_eq)|Эти операторы добавляют и вычитают объект `CTimeSpan` в этот `CTime` объект и из него.|
|[Оператор =](#operator_eq)|Оператор присваивания.|
|[operator = =, < и т. д.](#ctime_comparison_operators)|Операторы сравнения.|

## <a name="remarks"></a>Remarks

`CTime` не имеет базового класса.

`CTime` значения основаны на времени в формате UTC, которое эквивалентно всеобщему скоординированному времени (время по Гринвичу, GMT). Сведения о том, как определяется часовой пояс, см. в разделе [Управление временем](../../c-runtime-library/time-management.md) .

При создании объекта `CTime` задайте для параметра `nDST` значение 0, чтобы указать, что действует стандартное время, или значение больше 0, чтобы указать, что действует летнее время, или на значение меньше нуля, чтобы код библиотеки времени выполнения C вычислит, действует ли стандартное время или летнее время. `tm_isdst` — это обязательное поле. Если не задано, его значение не определено и возвращаемое значение из [функциях mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) является непредсказуемым. Если `timeptr` указывает на структуру TM, возвращенную предыдущим вызовом функции [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)или [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), поле `tm_isdst` содержит правильное значение.

Сопровождающий класс, [ктимеспан](../../atl-mfc-shared/reference/ctimespan-class.md), представляет интервал времени.

Классы `CTime` и `CTimeSpan` не предназначены для наследования. Поскольку нет виртуальных функций, размер `CTime` и `CTimeSpan` объектов составляет ровно 8 байт. Большинство функций членов являются встроенными.

> [!NOTE]
>  Верхний предел для даты равен 12/31/3000. Нижний предел — 1/1/1970 12:00:00 AM по ГРИНВИЧу.

Дополнительные сведения об использовании `CTime`см. в статьях [Дата и время](../../atl-mfc-shared/date-and-time.md)и [Управление временем](../../c-runtime-library/time-management.md) в справочнике по библиотеке времени выполнения.

> [!NOTE]
>  Структура `CTime` изменена с MFC 7,1 на MFC 8,0. При сериализации структуры `CTime` с помощью **оператора < <** в MFC 8,0 или более поздней версии полученный файл не будет доступен для чтения в более ранних версиях MFC.

## <a name="requirements"></a>Требования

**Заголовок:** атлтиме. h

##  <a name="ctime_comparison_operators"></a>Операторы сравнения CTime

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

Эти операторы сравнивают два абсолютных значения времени и возвращают значение TRUE, если условие истинно. в противном случае — FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>CTime:: CTime

Создает новый объект `CTime`, инициализируемый с указанным временем.

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

*тимесрк*<br/>
Указывает объект `CTime`, который уже существует.

*time*<br/>
Значение времени `__time64_t`, которое представляет собой количество секунд после 1 января 1970 UTC. Обратите внимание, что это значение будет изменено на местное время. Например, если вы используете Нью-Йорк и создаете объект `CTime`, передав параметр 0, [CTime::](#getmonth) GetObject возвратит 12.

*НЕАР*, *нмонс*, *nОшибка дня*, *nчас суток*, *nмин.* , *NSEC*<br/>
Указывает значения даты и времени, которые должны быть скопированы в новый объект `CTime`.

*ндст*<br/>
Указывает, действует ли летнее время. Может иметь одно из трех значений:

- для *НДСТ* задано значение 0Standard Time.

- для *НДСТ* задано значение больше, чем 0Daylight экономия времени.

- для *НДСТ* задано значение меньше 0The по умолчанию. Автоматически вычислит, действует ли стандартное время или летнее время.

*вдосдате*, *вдостиме*<br/>
Значения даты и времени MS-DOS, которые будут преобразованы в значение даты и времени и скопированы в новый объект `CTime`.

*день*<br/>
Структура [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , которую необходимо преобразовать в значение даты и времени и скопировать в новый объект `CTime`.

*ФТ*<br/>
Структура [fileTime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) , которую необходимо преобразовать в значение даты и времени и скопировать в новый объект `CTime`.

*DBTS*<br/>
Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.

### <a name="remarks"></a>Remarks

Каждый конструктор описан ниже.

- `CTime();` конструирует неинициализированный объект `CTime`. Этот конструктор позволяет определять `CTime` массивы объектов. Следует инициализировать такие массивы с допустимыми значениями времени перед использованием.

- `CTime( const CTime& );` конструирует объект `CTime` из другого значения `CTime`.

- `CTime( __time64_t );` конструирует объект `CTime` из типа **__time64_t** . Этот конструктор принимает время в формате UTC и преобразует результат в местное время перед сохранением результата.

- `CTime( int, int, ...);` создает объект `CTime` из компонентов локального времени с каждым компонентом, ограниченным следующими диапазонами:

   |Компонент|Диапазон|
   |---------------|-----------|
   |*неар*|1970-3000|
   |*нмонс*|1–12|
   |*nОшибка дня*|1–31|
   |*Nчас суток*|0-23|
   |*Nмин.*|0-59|
   |*nSec*|0-59|

   Этот конструктор выполняет соответствующее преобразование в формате UTC. Отладочная версия библиотека Microsoft Foundation Class утверждает, если один или несколько компонентов времени выходят за пределы диапазона. Перед вызовом необходимо проверить аргументы. Этот конструктор принимает местное время.

- `CTime( WORD, WORD );` конструирует объект `CTime` из указанных значений даты и времени MS-DOS. Этот конструктор принимает местное время.

- `CTime( const SYSTEMTIME& );` конструирует объект `CTime` из структуры `SYSTEMTIME`. Этот конструктор принимает местное время.

- `CTime( const FILETIME& );` конструирует объект `CTime` из структуры `FILETIME`. Скорее всего, вы не будете использовать `CTime FILETIME`ную инициализацию напрямую. Если для работы с файлом используется объект `CFile`, `CFile::GetStatus` извлекает метку времени файла для вас через объект `CTime`, инициализируемый структурой `FILETIME`. Этот конструктор предполагает время на основе времени в формате UTC и автоматически преобразует значение в местное время перед сохранением результата.

   > [!NOTE]
   > Конструктор, использующий параметр `DBTIMESTAMP`, доступен только при включении OLEDB. h.

Дополнительные сведения см. в разделе Структура [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) и [fileTime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) в Windows SDK. См. также запись [даты и времени MS-DOS](/windows/win32/SysInfo/ms-dos-date-and-time) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>CTime:: Format

Вызовите эту функцию-член для создания форматированного представления значения даты и времени.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*псзформат*<br/>
Строка форматирования, аналогичная строке форматирования `printf`. Коды форматирования, перед которыми предшествует знак процента (`%`), заменяются соответствующим компонентом `CTime`. Другие символы в строке форматирования копируются без изменений в возвращаемую строку. Список кодов форматирования см. в описании функции времени выполнения [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*нформатид*<br/>
Идентификатор строки, определяющей этот формат.

### <a name="return-value"></a>Возвращаемое значение

Значение [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащее отформатированное время.

### <a name="remarks"></a>Remarks

Если состояние этого `CTime` объекта равно null, то возвращаемое значение является пустой строкой.

Этот метод создает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 до 31 декабря 3000, время в формате UTC.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>CTime:: Форматгмт

Формирует отформатированную строку, соответствующую этому объекту `CTime`.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*псзформат*<br/>
Задает строку форматирования, похожую на строку форматирования `printf`. Дополнительные сведения см. в описании функции времени выполнения [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*нформатид*<br/>
Идентификатор строки, определяющей этот формат.

### <a name="return-value"></a>Возвращаемое значение

Значение [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащее отформатированное время.

### <a name="remarks"></a>Remarks

Значение времени не преобразуется, поэтому оно отражает время в формате UTC.

Этот метод создает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 до 31 декабря 3000, время в формате UTC.

### <a name="example"></a>Пример

См. пример для [CTime:: Format](#format).

##  <a name="getasdbtimestamp"></a>CTime:: Жетасдбтиместамп

Вызовите эту функцию-член для преобразования сведений о времени, хранящихся в объекте `CTime`, в структуру DBTIMESTAMP, совместимую с Win32.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Параметры

*DBTS*<br/>
Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Сохраняет полученное время в структуре *DBTS* , на которую указывает ссылка. В структуре данных `DBTIMESTAMP`, инициализированной этой функцией, `fraction` член имеет нулевое значение.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>CTime:: Жетассистемтиме

Вызовите эту функцию-член для преобразования сведений о времени, хранящихся в объекте `CTime`, в структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , совместимую с Win32.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Параметры

*тимедест*<br/>
Ссылка на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , которая будет содержать преобразованное значение даты и времени объекта `CTime`.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

`GetAsSystemTime` сохраняет результирующее время в указанной структуре *тимедест* . В структуре данных `SYSTEMTIME`, инициализированной этой функцией, `wMilliseconds` член имеет нулевое значение.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>CTime:: Жеткурренттиме

Возвращает объект `CTime`, представляющий текущее время.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Remarks

Возвращает текущую системную дату и время в формате UTC.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>CTime:: GetDay

Возвращает день, представленный объектом `CTime`.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает день месяца, основанный на местном времени, в диапазоне от 1 до 31.

### <a name="remarks"></a>Remarks

Эта функция вызывает `GetLocalTm`, которая использует внутренний, статически выделенный буфер. Данные в этом буфере перезаписываются из-за вызовов других функций-членов `CTime`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>CTime:: Жетдайофвик

Возвращает день недели, представленный объектом `CTime`.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает день недели, основанный на местном времени; 1 = воскресенье, 2 = понедельник, 7 = суббота.

### <a name="remarks"></a>Remarks

Эта функция вызывает `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этом буфере перезаписываются из-за вызовов других функций-членов `CTime`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>CTime:: Жетгмттм

Возвращает **структуру TM** , которая содержит декомпозицию времени, содержащегося в этом объекте `CTime`.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*PTM*<br/>
Указывает на буфер, который будет принимать данные времени. Если этот указатель имеет значение NULL, возникает исключение.

### <a name="return-value"></a>Возвращаемое значение

Указатель на заполненную **структуру TM** , как определено во время включения файла. Высоты. Сведения о структуре структуры см. в разделе [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Remarks

`GetGmtTm` Возвращает время в формате UTC.

*PTM* не может иметь значение null. Если необходимо вернуться к старому поведению, в котором *PTM* может иметь значение null, чтобы указать, что следует использовать внутренний, выделенный статический буфер, а затем отменить определение _SECURE_ATL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>CTime:: в час

Возвращает час, представленный объектом `CTime`.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает час, основанный на местном времени, в диапазоне от 0 до 23.

### <a name="remarks"></a>Remarks

Эта функция вызывает `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этом буфере перезаписываются из-за вызовов других функций-членов `CTime`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>CTime:: Жетлокалтм

Возвращает **структуру TM** , содержащую декомпозицию времени, содержащегося в этом объекте `CTime`.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*PTM*<br/>
Указывает на буфер, который будет принимать данные времени. Если этот указатель имеет значение NULL, возникает исключение.

### <a name="return-value"></a>Возвращаемое значение

Указатель на заполненную **структуру TM** , как определено во время включения файла. Высоты. Сведения о структуре структуры см. в разделе [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Remarks

`GetLocalTm` Возвращает местное время.

*PTM* не может иметь значение null. Если необходимо вернуться к старому поведению, в котором *PTM* может иметь значение null, чтобы указать, что следует использовать внутренний, выделенный статический буфер, а затем отменить определение _SECURE_ATL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>CTime:: Minute

Возвращает минуты, представленную объектом `CTime`.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает минуты в диапазоне от 0 до 59 в зависимости от местного времени.

### <a name="remarks"></a>Remarks

Эта функция вызывает `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этом буфере перезаписываются из-за вызовов других функций-членов `CTime`.

### <a name="example"></a>Пример

См. пример для в течение [часа](#gethour).

##  <a name="getmonth"></a>CTime:: в месяц

Возвращает месяц, представленный объектом `CTime`.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает месяц, основанный на местном времени, в диапазоне от 1 до 12 (1 = Январь).

### <a name="remarks"></a>Remarks

Эта функция вызывает `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этом буфере перезаписываются из-за вызовов других функций-членов `CTime`.

### <a name="example"></a>Пример

См. пример для [GetDay](#getday).

##  <a name="getsecond"></a>CTime:: в секунду

Возвращает второй объект, представленный объектом `CTime`.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает второй объект, основанный на местном времени, в диапазоне от 0 до 59.

### <a name="remarks"></a>Remarks

Эта функция вызывает `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этом буфере перезаписываются из-за вызовов других функций-членов `CTime`.

### <a name="example"></a>Пример

См. пример для в течение [часа](#gethour).

##  <a name="gettime"></a>CTime:: во время

Возвращает **__time64_t** значение для данного объекта `CTime`.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

`GetTime` будет возвращать количество секунд между текущим объектом `CTime` и 1 января 1970.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>CTime:: в г.

Возвращает год, представленный объектом `CTime`.

```
int GetYear();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает год, основанный на местном времени, в диапазоне от 1 января 1970 г. до 18 января 2038 (включительно).

### <a name="remarks"></a>Remarks

Эта функция вызывает `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этом буфере перезаписываются из-за вызовов других функций-членов `CTime`.

### <a name="example"></a>Пример

См. пример для [GetDay](#getday).

##  <a name="operator_eq"></a>CTime:: operator =

Оператор присваивания.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Параметры

*time*<br/>
Новое значение даты и времени.

### <a name="return-value"></a>Возвращаемое значение

Обновленный объект `CTime`.

### <a name="remarks"></a>Remarks

Этот перегруженный оператор присваивания копирует время источника в этот объект `CTime`. Внутреннее хранилище времени в объекте `CTime` не зависит от часового пояса. Во время назначения Преобразование часового пояса не требуется.

##  <a name="operator_add_-"></a>CTime:: operator +,-

Эти операторы добавляют и вычитают `CTimeSpan` и `CTime` объекты.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Параметры

*Временной*<br/>
Добавляемый или вычитаемый объект `CTimeSpan`.

*time*<br/>
Объект `CTime` для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Объект `CTime` или `CTimeSpan`, представляющий результат операции.

### <a name="remarks"></a>Remarks

`CTime` объекты представляют абсолютное время, `CTimeSpan` объекты представляют относительное время. Первые два оператора позволяют добавлять и вычитать `CTimeSpan` объекты в `CTime` объекты и из них. Третий оператор позволяет вычесть один объект `CTime` из другого, чтобы получить объект `CTimeSpan`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>CTime:: operator + =,-=

Эти операторы добавляют и вычитают объект `CTimeSpan` в этот `CTime` объект и из него.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Добавляемый или вычитаемый объект `CTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Обновленный объект `CTime`.

### <a name="remarks"></a>Remarks

Эти операторы позволяют добавлять объект `CTimeSpan` в этот `CTime` объект и вычитать его.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>CTime:: Serialize64

> [!NOTE]
> Этот метод доступен только в проектах MFC.

Сериализует данные, связанные с переменной члена, в архив или из архива.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*<br/>
Объект `CArchive`, который требуется обновить.

### <a name="return-value"></a>Возвращаемое значение

Обновленный объект `CArchive`.

## <a name="see-also"></a>См. также раздел

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
