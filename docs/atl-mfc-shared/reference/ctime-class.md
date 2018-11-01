---
title: Класс CTime
ms.date: 10/18/2018
f1_keywords:
- CTime
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
ms.openlocfilehash: bed403e4bc1cca1d31a394be7157de9e65abff95
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519448"
---
# <a name="ctime-class"></a>Класс CTime

Представляет абсолютное время и дату.

## <a name="syntax"></a>Синтаксис

```
class CTime
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTime::CTime](#ctime)|Создает `CTime` объекты различными способами.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTime::Format](#format)|Преобразует `CTime` объекта в форматированную строку, в зависимости от местного часового пояса.|
|[CTime::FormatGmt](#formatgmt)|Преобразует `CTime` объекта в форматированную строку — исчисляется по UTC.|
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Преобразует время сведениями, хранящимися в `CTime` объекта на структуру Win32-совместимых DBTIMESTAMP.|
|[CTime::GetAsSystemTime](#getassystemtime)|Преобразует время сведениями, хранящимися в `CTime` в Win32-совместимый [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.|
|[CTime::GetCurrentTime](#getcurrenttime)|Создает `CTime` объект, представляющий текущее время (статическая функция-член).|
|[CTime::GetDay](#getday)|Возвращает день представлен `CTime` объекта.|
|[CTime::GetDayOfWeek](#getdayofweek)|Возвращает день недели, представленный `CTime` объекта.|
|[CTime::GetGmtTm](#getgmttm)|Разбивает `CTime` объекта в виде компонентов — исчисляется по UTC.|
|[CTime::GetHour](#gethour)|Возвращает час, представленный `CTime` объекта.|
|[CTime::GetLocalTm](#getlocaltm)|Разбивает `CTime` объекта на компоненты, зависимости от местного часового пояса.|
|[CTime::GetMinute](#getminute)|Возвращается значение минут, представленного `CTime` объекта.|
|[CTime::GetMonth](#getmonth)|Возвращает номер месяца, представленный `CTime` объекта.|
|[CTime::GetSecond](#getsecond)|Возвращает вторую от представленного `CTime` объекта.|
|[CTime::GetTime](#gettime)|Возвращает **__time64_t** значение для заданного `CTime` объекта.|
|[CTime::GetYear](#getyear)|Возвращает значение года, представленный `CTime` объекта.|
|[CTime::Serialize64](#serialize64)|Сериализует данные из архива.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор + -](#operator_add_-)|Эти операторы сложения и вычитания `CTimeSpan` и `CTime` объектов.|
|[оператор +=-=](#operator_add_eq_-_eq)|Эти операторы сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.|
|[оператор =](#operator_eq)|Оператор присваивания.|
|[оператор ==, < и т. д.](#ctime_comparison_operators)|Операторы сравнения.|

## <a name="remarks"></a>Примечания

`CTime` не имеет базового класса.

`CTime` значения основаны на формате общего скоординированного времени (UTC), что эквивалентно формате UTC (время по Гринвичу, GMT). См. в разделе [управление временем](../../c-runtime-library/time-management.md) сведения о том, как определяется часовой пояс.

При создании `CTime` установите `nDST` параметра равным 0, чтобы указать, что действует стандартное время, или значение больше 0, чтобы указать, что летнего времени действует, или значение меньше нуля, чтобы указать ная код библиотеки времени выполнения C e (зима) или летнее время, является ли в силе. `tm_isdst` — это обязательное поле. Если не задано, его значение не определено и возвращаемое значение из [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) непредсказуем. Если `timeptr` указывает на структуру tm, возвращенный предыдущим вызовом [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), или [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` поле содержит правильное значение.

Вспомогательный класс, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), представляющий интервал времени.

`CTime` И `CTimeSpan` классы не предназначены для наследования. Так как нет виртуальных функций, размер `CTime` и `CTimeSpan` объекты — ровно 8 байт. Большинство функций-членов приведены в коде.

> [!NOTE]
>  Первая дата в это значение равно 12/31/3000. Нижний предел — 1/1/1970 г. 12:00:00 AM GMT.

Дополнительные сведения об использовании `CTime`, см. в статьях [даты и времени](../../atl-mfc-shared/date-and-time.md), и [управление временем](../../c-runtime-library/time-management.md) справочника по библиотеке времени выполнения.

> [!NOTE]
>  `CTime` Структура изменилось с MFC 7.1 до MFC 8.0. При сериализации `CTime` структуры с помощью **оператор <<** в MFC 8.0 или более поздней версии, полученный файл не будет прочитать в старых версиях MFC.

## <a name="requirements"></a>Требования

**Заголовок:** atltime.h

##  <a name="ctime_comparison_operators"></a>  Операторы сравнения CTime

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

Эти операторы сравнивают два абсолютный раз и возвращает значение TRUE, если условие равно true; в противном случае — значение FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>  CTime::CTime

Создает новый `CTime` объект инициализирован с указанного времени.

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
Объект `__time64_t` значение времени, которое является количество секунд после 1 января 1970 года в формате UTC. Обратите внимание на то, что это будет впоследствии скорректирована местное время. Например, если находятся в Нью-Йорк и создайте `CTime` объекта, передав параметр 0, [CTime::GetMonth](#getmonth) возвращает 12.

*nYear*, *nMonth*, *nDay*, *основе Nчас*, *Nмин.*, *nSec*<br/>
Указывает, значений даты и времени, который необходимо скопировать в новый `CTime` объекта.

*nDST*<br/>
Указывает, действует ли летнее время. Может иметь одно из трех значений:

- *nDST* наборов 0Standard время.

- *nDST* присвоено значение больше, чем 0Daylight экономии времени.

- *nDST* присвоено значение меньше, чем 0The по умолчанию. Автоматически вычисляет стандартное время или летнее время действует ли.

*wDosDate*, *wDosTime*<br/>
Значения даты и времени MS-DOS, которые следует преобразовать в значение даты и времени и скопировать в новый `CTime` объекта.

*ST*<br/>
Объект [SYSTEMTIME](../../mfc/reference/systemtime-structure.md) структуры, которые следует преобразовать в значение даты и времени и скопировать в новый `CTime` объекта.

*FT*<br/>
Объект [FILETIME](../../mfc/reference/filetime-structure.md) структуры, которые следует преобразовать в значение даты и времени и скопировать в новый `CTime` объекта.

*DBTS*<br/>
Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.

### <a name="remarks"></a>Примечания

Каждый конструктор описан ниже.

- `CTime();` Создает неинициализированный `CTime` объекта. Этот конструктор позволяет определить `CTime` объекта массивов. Такие массивы с допустимым временем перед использованием необходимо инициализировать.

- `CTime( const CTime& );` Создает `CTime` из другого объекта `CTime` значение.

- `CTime( __time64_t );` Создает `CTime` объекта из **__time64_t** типа. Этот конструктор ожидает, что время в формате UTC и преобразует результат в местное время, прежде чем сохранить результат.

- `CTime( int, int, ...);` Создает `CTime` объект из компонентов местного времени с каждым компонентом ограничен следующие диапазоны:

   |Компонент|Диапазон|
   |---------------|-----------|
   |*nYear*|1970-3000|
   |*nMonth*|1–12|
   |*nDay*|1–31|
   |*основе Nчас*|0-23|
   |*Nмин.*|0-59|
   |*nSec*|0-59|

   Этот конструктор создает соответствующее преобразование в формат UTC. Отладочную версию библиотеки Microsoft Foundation Class утверждений, если один или несколько компонентов времени выходят за пределы диапазона. Необходимо проверить перед вызовом аргументы. Этот конструктор ожидает, что местное время.

- `CTime( WORD, WORD );` Создает `CTime` объект из указанного значения даты и времени MS-DOS. Этот конструктор ожидает, что местное время.

- `CTime( const SYSTEMTIME& );` Создает `CTime` объекта из `SYSTEMTIME` структуры. Этот конструктор ожидает, что местное время.

- `CTime( const FILETIME& );` Создает `CTime` объекта из `FILETIME` структуры. Скорее всего, вы не будете использовать `CTime FILETIME` инициализации напрямую. При использовании `CFile` объекта для работы с файлом `CFile::GetStatus` извлекает файл отметку времени для вас через `CTime` инициализированный с помощью `FILETIME` структуры. Этот конструктор предполагает время исчисляется по UTC и автоматически преобразует значение в местное время, прежде чем сохранить результат.

   > [!NOTE]
   > В конструктор с помощью `DBTIMESTAMP` параметр доступен только в случае, если включен OLEDB.h.

Дополнительные сведения см. в разделе [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](https://msdn.microsoft.com/library/windows/desktop/ms724284) структуры в пакете Windows SDK. Также см. в разделе [MS-DOS даты и времени](/windows/desktop/SysInfo/ms-dos-date-and-time) запись в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>  CTime::Format

Эта функция члена для создания отформатированное представление значения даты и времени.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Форматирование строки аналогичную `printf` форматирования строки. Коды, предшествует процента форматирования (`%`) выполните вход, заменен соответствующим `CTime` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Функции времени выполнения см. в разделе [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) список кодов форматирования.

*nFormatID*<br/>
Идентификатор строки, который определяет этот формат.

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий времени в формате.

### <a name="remarks"></a>Примечания

Если состояние данного объекта `CTime` объект имеет значение null, возвращаемое значение является пустой строкой.

Этот метод вызывает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 года до 31 декабря 3000 всеобщее скоординированное время (UTC).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>  CTime::FormatGmt

Создает форматированную строку, соответствующий этому `CTime` объекта.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Задает строку форматирования, аналогичную `printf` форматирования строки. Функции времени выполнения см. в разделе [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) подробные сведения.

*nFormatID*<br/>
Идентификатор строки, который определяет этот формат.

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий времени в формате.

### <a name="remarks"></a>Примечания

Значение времени не преобразуется и таким образом отражает UTC.

Этот метод вызывает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 года до 31 декабря 3000 всеобщее скоординированное время (UTC).

### <a name="example"></a>Пример

См. в примере [CTime::Format](#format).

##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP

Вызовите эту функцию-член для преобразования времени информацию, хранящуюся в `CTime` объекта на структуру Win32-совместимых DBTIMESTAMP.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Параметры

*DBTS*<br/>
Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Сохраняет полученное время для упоминаемого *dbts* структуры. `DBTIMESTAMP` Структура данных инициализируется при помощи этой функции будет иметь его `fraction` имеет нулевое значение члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime

Вызовите эту функцию-член для преобразования времени информацию, хранящуюся в `CTime` в Win32-совместимый [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Параметры

*timeDest*<br/>
Ссылку на [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая будет хранить значение преобразованного даты и времени `CTime` объекта.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

`GetAsSystemTime` сохраняет полученное время для упоминаемого *timeDest* структуры. `SYSTEMTIME` Структура данных инициализируется при помощи этой функции будет иметь его `wMilliseconds` имеет нулевое значение члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>  CTime::GetCurrentTime

Возвращает `CTime` , представляющий текущее время.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Примечания

Возвращает текущую системную дату и время в формате UTC (UTC).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>  CTime::GetDay

Возвращает день представлен `CTime` объекта.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает день месяца, с локального времени, в диапазоне от 1 до 31.

### <a name="remarks"></a>Примечания

Эта функция вызывает `GetLocalTm`, которая использует внутренний статически выделяемый буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функций-членов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek

Возвращает день недели, представленный `CTime` объекта.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает день недели, на основе локального времени; 1 = воскресенье, 2 = понедельник, 7 = суббота.

### <a name="remarks"></a>Примечания

Эта функция вызывает `GetLocalTm`, который использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функций-членов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>  CTime::GetGmtTm

Получает **struct tm** , содержащий декомпозиции времени, содержащихся в данном `CTime` объекта.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*ptm*<br/>
Указывает на буфер, получающий данные времени. Если этот указатель имеет значение NULL, создается исключение.

### <a name="return-value"></a>Возвращаемое значение

Указатель на заполненными **struct tm** как определено во включаемом файле времени. З. См. в разделе [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) для компоновке структуры.

### <a name="remarks"></a>Примечания

`GetGmtTm` Возвращает в формате UTC.

*ptm* не может иметь значение NULL. Если вы хотите вернуться к старому поведению, в котором *ptm* может иметь значение NULL указывает, что произошла внутренняя, необходимо использовать статически выделенный буфер, затем отменить _SECURE_ATL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>  CTime::GetHour

Возвращает час, представленный `CTime` объекта.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает час, с локального времени, в диапазоне от 0 до 23.

### <a name="remarks"></a>Примечания

Эта функция вызывает `GetLocalTm`, который использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функций-членов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>  CTime::GetLocalTm

Получает **struct tm** содержащий декомпозиции времени, содержащихся в данном `CTime` объекта.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*ptm*<br/>
Указывает на буфер, получающий данные времени. Если этот указатель имеет значение NULL, создается исключение.

### <a name="return-value"></a>Возвращаемое значение

Указатель на заполненными **struct tm** как определено во включаемом файле времени. З. См. в разделе [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) для компоновке структуры.

### <a name="remarks"></a>Примечания

`GetLocalTm` Возвращает местное время.

*ptm* не может иметь значение NULL. Если вы хотите вернуться к старому поведению, в котором *ptm* может иметь значение NULL указывает, что произошла внутренняя, необходимо использовать статически выделенный буфер, затем отменить _SECURE_ATL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>  CTime::GetMinute

Возвращается значение минут, представленного `CTime` объекта.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает минуты в зависимости от местное время, в диапазоне от 0 до 59.

### <a name="remarks"></a>Примечания

Эта функция вызывает `GetLocalTm`, который использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функций-членов.

### <a name="example"></a>Пример

См. в примере [GetHour](#gethour).

##  <a name="getmonth"></a>  CTime::GetMonth

Возвращает номер месяца, представленный `CTime` объекта.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает номер месяца, с локального времени, в диапазоне от 1 до 12 (1 = январь).

### <a name="remarks"></a>Примечания

Эта функция вызывает `GetLocalTm`, который использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функций-членов.

### <a name="example"></a>Пример

См. в примере [GetDay](#getday).

##  <a name="getsecond"></a>  CTime::GetSecond

Возвращает вторую от представленного `CTime` объекта.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает секунды в зависимости от местное время, в диапазоне от 0 до 59.

### <a name="remarks"></a>Примечания

Эта функция вызывает `GetLocalTm`, который использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функций-членов.

### <a name="example"></a>Пример

См. в примере [GetHour](#gethour).

##  <a name="gettime"></a>  CTime::GetTime

Возвращает **__time64_t** значение для заданного `CTime` объекта.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

`GetTime` Возвращает время в секундах между текущим `CTime` объекта и 1 января 1970 года.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>  CTime::GetYear

Возвращает значение года, представленный `CTime` объекта.

```
int GetYear();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение года, с локального времени, в диапазоне от января 1,1970 для 18 января 2038 (включительно).

### <a name="remarks"></a>Примечания

Эта функция вызывает `GetLocalTm`, который использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функций-членов.

### <a name="example"></a>Пример

См. в примере [GetDay](#getday).

##  <a name="operator_eq"></a>  CTime::operator =

Оператор присваивания.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Параметры

*time*<br/>
Значение нового даты и времени.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CTime` объекта.

### <a name="remarks"></a>Примечания

Этот оператор назначения перегруженных копирует источника времени в этот `CTime` объекта. Внутреннее время хранения в `CTime` объекта не зависит от часового пояса. Преобразование часового пояса не требуется во время назначения.

##  <a name="operator_add_-"></a>  CTime::operator +, -

Эти операторы сложения и вычитания `CTimeSpan` и `CTime` объектов.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Параметры

*интервал времени*<br/>
`CTimeSpan` Объект добавляемое или вычитаемое.

*time*<br/>
`CTime` Объект, который будет вычтен.

### <a name="return-value"></a>Возвращаемое значение

Объект `CTime` или `CTimeSpan` объект, представляющий результат операции.

### <a name="remarks"></a>Примечания

`CTime` объекты представляют абсолютное время `CTimeSpan` объекты представляют относительного времени. Первые два операторы позволяют сложения и вычитания `CTimeSpan` объектов и обратно `CTime` объектов. Третий оператор позволяет вычесть единицу `CTime` из другого для получения объекта `CTimeSpan` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  CTime::operator +=-=

Эти операторы сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*диапазон*<br/>
`CTimeSpan` Объект добавляемое или вычитаемое.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CTime` объекта.

### <a name="remarks"></a>Примечания

Эти операторы позволяют сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>  CTime::Serialize64

> [!NOTE]
> Этот метод доступен только в проектах MFC.

Сериализует данные, связанные с переменной-члена или из архива.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
`CArchive` Объект, который требуется обновить.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CArchive` объекта.

## <a name="see-also"></a>См. также

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
