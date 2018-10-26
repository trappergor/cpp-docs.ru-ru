---
title: Класс CFileTime | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
dev_langs:
- C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36e71cd975ff138343770b80e60b0287faa32558
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808827"
---
# <a name="cfiletime-class"></a>Класс CFileTime

Этот класс предоставляет методы для управления значений даты и времени, связанного с файлом.

## <a name="syntax"></a>Синтаксис

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFileTime::CFileTime](#cfiletime)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFileTime::GetCurrentTime](#getcurrenttime)|Вызовите эту статическую функцию для получения `CFileTime` объект, представляющий текущую системную дату и время.|
|[CFileTime::GetTime](#gettime)|Вызовите этот метод, чтобы получить время из `CFileTime` объекта.|
|[CFileTime::LocalToUTC](#localtoutc)|Вызовите этот метод для преобразования местного времени во время файла, на основе в формате UTC (UTC).|
|[CFileTime::SetTime](#settime)|Вызовите этот метод, чтобы указать дату и время, хранящихся в `CFileTime` объекта.|
|[CFileTime::UTCToLocal](#utctolocal)|Этот метод используется для преобразования времени в формате UTC (UTC) для местного времени.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CFileTime::operator-](#operator_-)|Этот оператор используется для вычитания `CFileTime` или `CFileTimeSpan` объекта.|
|[CFileTime::operator! =](#operator_neq)|Этот оператор сравнивает два `CFileTime` объектов на предмет их неравенства.|
|[CFileTime::operator +](#operator_add)|Этот оператор используется для сложения объекта `CFileTimeSpan`.|
|[CFileTime::operator +=](#operator_add_eq)|Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.|
|[CFileTime::operator &lt;](#operator_lt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.|
|[CFileTime::operator &lt;=](#operator_lt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.|
|[CFileTime::operator =](#operator_eq)|Оператор присваивания.|
|[CFileTime::operator-=](#operator_-_eq)|Этот оператор используется для вычитания `CFileTimeSpan` объекта и присвоить его результат в текущий объект.|
|[CFileTime::operator ==](#operator_eq_eq)|Этот оператор сравнивает два объекта `CFileTime` на равенство.|
|[CFileTime::operator &gt;](#operator_gt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.|
|[CFileTime::operator &gt;=](#operator_gt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[CFileTime::Day](#day)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих один день.|
|[CFileTime::Hour](#hour)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих один час.|
|[CFileTime::Millisecond](#millisecond)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих до одной миллисекунды.|
|[CFileTime::Minute](#minute)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну минуту.|
|[CFileTime::Second](#second)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну секунду.|
|[CFileTime::Week](#week)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну неделю.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для управления значения даты и времени, связанные с создания, доступа и изменения файлов. Методы и данные этого класса часто используются в сочетании с `CFileTimeSpan` объекты, которые обрабатывать значения относительного времени.

Значение даты и времени сохраняется как 64-разрядное значение, представляющее количество 100-наносекундных интервалов с 1 января 1601 года. Это формат по Гринвичу (UTC).

Следующие статические const переменных-членов предоставляются для упрощения вычислений:

|Переменная-член|Число 100-наносекундных интервалов|
|---------------------|-----------------------------------------|
|Millisecond|10,000|
|Second|Миллисекунды \* 1000|
|Minute|Второй \* 60|
|Hour|Минуты \* 60|
|Day|Час \* 24|
|Неделя|День \* 7|

**Примечание** не всем файловым системам можно записать создания и время последнего доступа и не все файловые системы запись их таким же образом. Для примера, в файловой системе FAT Windows NT, создать времени имеет разрешение 10 миллисекунд, время записи с разрешением 2 секунды и время доступа с разрешением 1 день (дата доступа). Для файловой системы NTFS время доступа с разрешением 1 час. Кроме того FAT записывает время на диске в формате местного времени, но NTFS записывает время на диске в формате UTC. Дополнительные сведения см. в разделе [времени файлов](/windows/desktop/SysInfo/file-times).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FILETIME`

`CFileTime`

## <a name="requirements"></a>Требования

**Заголовок:** atltime.h

##  <a name="cfiletime"></a>  CFileTime::CFileTime

Конструктор.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
Объект [FILETIME](https://msdn.microsoft.com/library/windows/desktop/ms724284) структуры.

*nTime*<br/>
Дата и время, выраженное как 64-разрядное значение.

### <a name="remarks"></a>Примечания

`CFileTime` Объект может быть создан с помощью существующих даты и времени из `FILETIME` структуры или выраженный 64-разрядное значение (в локальной или форматов времени в формате UTC (UTC)). Конструктор по умолчанию устанавливает время 0.

##  <a name="day"></a>  CFileTime::Day

Статические данные-член хранить число 100-наносекундных интервалов, составляющих один день.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Пример

См. в примере [CFileTime::Millisecond](#millisecond).

##  <a name="getcurrenttime"></a>  CFileTime::GetCurrentTime

Вызовите эту статическую функцию для получения `CFileTime` объект, представляющий текущую системную дату и время.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущую системную дату и время в формате UTC (UTC) формате.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

##  <a name="gettime"></a>  CFileTime::GetTime

Вызовите этот метод, чтобы получить время из `CFileTime` объекта.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дату и время в виде 64-разрядное число, которое может быть в локальной или форматирования в формате UTC (UTC).

##  <a name="hour"></a>  CFileTime::Hour

Статические данные-член хранить число 100-наносекундных интервалов, составляющих один час.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Пример

См. в примере [CFileTime::Millisecond](#millisecond).

##  <a name="localtoutc"></a>  CFileTime::LocalToUTC

Вызовите этот метод для преобразования местного времени во время файла, на основе в формате UTC (UTC).

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объект, содержащий время в формате UTC.

### <a name="example"></a>Пример

См. в примере [CFileTime::UTCToLocal](#utctolocal).

##  <a name="millisecond"></a>  CFileTime::Millisecond

Статические данные-член хранить число 100-наносекундных интервалов, составляющих до одной миллисекунды.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

##  <a name="minute"></a>  CFileTime::Minute

Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну минуту.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Пример

См. в примере [CFileTime::Millisecond](#millisecond).

##  <a name="operator_-"></a>  CFileTime::operator-

Этот оператор используется для вычитания `CFileTime` или `CFileTimeSpan` объекта.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*<br/>
Объект `CFileTimeSpan`.

*FT*<br/>
Объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объекта или `CFileTimeSpan` объект, представляющий результат разницу между двумя объектами.

##  <a name="operator_neq"></a>  CFileTime::operator! =

Этот оператор сравнивает два `CFileTime` объектов на предмет их неравенства.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент с которым производится сравнение не равно `CFileTime` объекта, в противном случае — значение FALSE.

##  <a name="operator_add"></a>  CFileTime::operator +

Этот оператор используется для сложения объекта `CFileTimeSpan`.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*<br/>
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объект, представляющий результат исходного времени, а также относительного времени.

##  <a name="operator_add_eq"></a>  CFileTime::operator +=

Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*диапазон*<br/>
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTime` объект, представляющий результат исходного времени, а также относительного времени.

##  <a name="operator_lt"></a>  CFileTime::operator &lt;

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше (ранее во времени) второй, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

##  <a name="operator_lt_eq"></a>  CFileTime::operator &lt;=

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект "меньше" (ранее времени) или равно значению второго, в противном случае — значение FALSE.

##  <a name="operator_eq"></a>  CFileTime::operator =

Оператор присваивания.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
Объект `CFileTime` объект, содержащий новое значение времени и даты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTime` объекта.

##  <a name="operator_-_eq"></a>  CFileTime::operator-=

Этот оператор используется для вычитания `CFileTimeSpan` объекта и присвоить его результат в текущий объект.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*диапазон*<br/>
Объект `CFileTimeSpan` объект, содержащий относительного времени для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTime` объекта.

##  <a name="operator_eq_eq"></a>  CFileTime::operator ==

Этот оператор сравнивает два объекта `CFileTime` на равенство.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
`CFileTime` Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты равны, в противном случае — значение FALSE.

##  <a name="operator_gt"></a>  CFileTime::operator &gt;

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше, чем (позднее по времени) второго, в противном случае — значение FALSE.

##  <a name="operator_gt_eq"></a>  CFileTime::operator &gt;=

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*FT*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше (позднее по времени) или равен ему, в противном случае — значение FALSE.

##  <a name="second"></a>  CFileTime::Second

Статические данные-член хранить число 100-наносекундных интервалов, составляющих один день.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Пример

См. в примере [CFileTime::Millisecond](#millisecond).

##  <a name="settime"></a>  CFileTime::SetTime

Вызовите этот метод, чтобы указать дату и время, хранящихся в `CFileTime` объекта.

```
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Параметры

*nTime*<br/>
64-разрядное значение, представляющее дату и время, в локальной или форматирования в формате UTC (UTC).

##  <a name="utctolocal"></a>  CFileTime::UTCToLocal

Этот метод используется для преобразования времени в формате UTC (UTC) для местного времени.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объекта, содержащее время в формате времени локального файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

##  <a name="week"></a>  CFileTime::Week

Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну неделю.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Пример

См. в примере [CFileTime::Millisecond](#millisecond).

## <a name="see-also"></a>См. также

[FILETIME](https://msdn.microsoft.com/library/windows/desktop/ms724284)<br/>
[Класс CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
