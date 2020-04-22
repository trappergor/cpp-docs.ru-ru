---
title: Класс ColeDateTimeSpan
ms.date: 03/27/2019
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
ms.openlocfilehash: 8f6a26c2724146f8723dee3ddce60ddce6995ec8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747152"
---
# <a name="coledatetimespan-class"></a>Класс ColeDateTimeSpan

Представляет относительное время, промежуток времени.

## <a name="syntax"></a>Синтаксис

```
class COleDateTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDateTimeSpan:: COleDateTimeSpan](#coledatetimespan)|Формирует объект `COleDateTimeSpan`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDateTimeSpan::Формат](#format)|Генерирует отформатированный строковый `COleDateTimeSpan` репрезентации объекта.|
|[COleDateTimeSpan::GetDays](#getdays)|Возвращает дневную часть диапазона, который представляет этот `COleDateTimeSpan` объект.|
|[COleDateTimeSpan::GetHours](#gethours)|Возвращает часовую часть диапазона, который представляет этот `COleDateTimeSpan` объект.|
|[COleDateTimeSpan::GetMinutes](#getminutes)|Возвращает минутную часть диапазона, который представляет этот `COleDateTimeSpan` объект.|
|[COleDateTimeSpan::GetSeconds](#getseconds)|Возвращает вторую часть пролета, который представляет этот `COleDateTimeSpan` объект.|
|[COleDateTimeSpan::GetStatus](#getstatus)|Получает статус (действительность) `COleDateTimeSpan` этого объекта.|
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Возвращает количество дней, `COleDateTimeSpan` которые представляет этот объект.|
|[COleDateTimeSpan:GetTotalHours](#gettotalhours)|Возвращает количество часов, `COleDateTimeSpan` которые представляет этот объект.|
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает количество минут, `COleDateTimeSpan` которые представляет этот объект.|
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает количество секунд, `COleDateTimeSpan` которые представляет этот объект.|
|[ColeDateTimeSpan::SetDateSpan](#setdatetimespan)|Устанавливает значение этого `COleDateTimeSpan` объекта.|
|[ColeDateTimeSpan::SetStatus](#setstatus)|Устанавливает статус (действительность) `COleDateTimeSpan` этого объекта.|

### <a name="public-operators"></a>Открытые операторы

|||
|-|-|
|[оператор No, -](#operator_add_-)|Добавление, вычитание и `COleDateTimeSpan` изменение знака для значений.|
|[оператором, --](#operator_add_eq_-_eq)|Добавить и `COleDateTimeSpan` вычесть `COleDateTimeSpan` значение из этого значения.|
|[Оператор](#operator_eq)|Копирует `COleDateTimeSpan` значение.|
|[оператор, <, <](#coledatetimespan_relational_operators)|Сравните `COleDateTimeSpan` два значения.|
|[double - оператор](#operator_double)|Преобразует это `COleDateTimeSpan` значение в **двойное.**|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleDateTimeSpan::m_span](#m_span)|Содержит базовый **двойник** для этого `COleDateTimeSpan` объекта.|
|[COleDateTimeSpan::m_status](#m_status)|Содержит статус этого `COleDateTimeSpan` объекта.|

## <a name="remarks"></a>Remarks

`COleDateTimeSpan`не имеет базового класса.

Сохраняет `COleDateTimeSpan` время в днях.

`COleDateTimeSpan`используется со своим сопутствующим классом [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime`инкапсулирует тип `DATE` данных автоматизации OLE. `COleDateTime`представляет абсолютные значения времени. Все `COleDateTime` расчеты включают `COleDateTimeSpan` значения. Связь между этими классами аналогична взаимосвязи между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan.](../../atl-mfc-shared/reference/ctimespan-class.md)

Для получения дополнительной `COleDateTime` `COleDateTimeSpan` информации о [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)классах и классах, см.

## <a name="requirements"></a>Требования

**Заголовок:** ATLComTime.h

## <a name="coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a>COleDateTimeSpan Реляционные Операторы

Операторы сравнения.

```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```

### <a name="parameters"></a>Параметры

*dateSpan*<br/>
Объект `COleDateTimeSpan` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Эти операторы сравнивают два значения даты/времени и возвращают TRUE, если условие верно; в противном случае FALSE.

### <a name="remarks"></a>Remarks

> [!NOTE]
> ATLASSERT будет происходить, если любой operand является недействительным.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

## <a name="coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a>COleDateTimeSpan:: COleDateTimeSpan

Формирует объект `COleDateTimeSpan`.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*dblSpanSrc*<br/>
Количество дней, которые будут скопированы в новый `COleDateTimeSpan` объект.

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Укажите значения дня и времени, которые `COleDateTimeSpan` будут скопированы в новый объект.

### <a name="remarks"></a>Remarks

Все эти конструкторы создают `COleDateTimeSpan` новые объекты, инициализированные к заданному значению. Краткое описание каждого из этих конструкторов следующим образом:

- **COleDateTimeSpan ()** Строит объект, `COleDateTimeSpan` инициализированный к 0.

- **COleDateTimeSpan** `dblSpanSrc` **()** Строит `COleDateTimeSpan` объект из значения плавающей точки.

- **COleDateTimeSpan(,** `lDays` **,** `nHours` **,** `nMins` **)** `nSecs` **)** Строит объект, `COleDateTimeSpan` инициализированный к указанным численным значениям.

Статус нового `COleDateTimeSpan` объекта установлен в действии.

Для получения дополнительной информации `COleDateTimeSpan` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

## <a name="coledatetimespanformat"></a><a name="format"></a>COleDateTimeSpan::Формат

Генерирует отформатированный строковый `COleDateTimeSpan` репрезентации объекта.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Параметры

*pФормат*<br/>
Строка форматирования, `printf` похожая на строку форматирования. Коды форматирования, предшествующий знаку процента`%` `COleDateTimeSpan` () заменяются соответствующим компонентом. Другие символы строки форматирования копируются без изменений в возвращенную строку. Значение и значение кодов форматирования `Format` для приведены ниже:

- **%H** Часы в текущем дне

- **%M** Минуты в текущем часе

- **%S** Секунды в текущей минуте

- **%%** Процент наяпийк

Четыре кода формата, перечисленные выше, являются единственными кодами, которые будет принимать Format.

-

*nID*<br/>
Идентификатор ресурса для строки управления форматом.

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий отформатированную дату/значение времени.

### <a name="remarks"></a>Remarks

Вызовите эти функции, чтобы создать отформатированный представление значения промежутка времени. Если состояние этого `COleDateTimeSpan` объекта является нулевым, значение возврата является пустой строкой. Если статус недействителен, строка возврата указывается ресурсом строки IDS_INVALID_DATETIMESPAN.

Краткое описание форм для этой функции следующим образом:

**Формат** *(pFormat* **)**<br/>
Эта форма форматирует значение с помощью строки формата, которая содержит специальные `printf`коды форматирования, которым предшествует знак процента (%), как в . Строка форматирования передается в качестве параметра функции.

**Формат** *(nID)* **)**<br/>
Эта форма форматирует значение с помощью строки формата, которая содержит специальные `printf`коды форматирования, которым предшествует знак процента (%), как в . Строка форматирования — это ресурс. Идентификатор этого ресурса строки передается как параметр.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

## <a name="coledatetimespangetdays"></a><a name="getdays"></a>COleDateTimeSpan::GetDays

Извлекает дневную часть этого значения даты/времени.пролет.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Дневная часть значения этой даты/времени действия.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются от приблизительно - 3 615 000 и 3 615 000.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

## <a name="coledatetimespangethours"></a><a name="gethours"></a>COleDateTimeSpan::GetHours

Извлекает часовую часть этого значения даты/времени.пролет.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часовая часть этой даты/значения времени.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются между 23 и 23.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetDays](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

## <a name="coledatetimespangetminutes"></a><a name="getminutes"></a>COleDateTimeSpan::GetMinutes

Извлекает минутную часть этого значения даты/времени.пролет.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Минутная часть этого значения даты/времени действия.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются между 59 и 59.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

## <a name="coledatetimespangetseconds"></a><a name="getseconds"></a>COleDateTimeSpan::GetSeconds

Извлекает вторую часть значения даты/времени.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Секундная часть значения этой даты/времени действия.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются между 59 и 59.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

## <a name="coledatetimespangetstatus"></a><a name="getstatus"></a>COleDateTimeSpan::GetStatus

Получает статус (действительность) `COleDateTimeSpan` этого объекта.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние этого `COleDateTimeSpan` значения.

### <a name="remarks"></a>Remarks

Значение возврата определяется `DateTimeSpanStatus` перечисленным типом, который определяется `COleDateTimeSpan` в классе.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

Краткое описание этих значений статуса см.

- `COleDateTimeSpan::valid`Означает, `COleDateTimeSpan` что этот объект является действительным.

- `COleDateTimeSpan::invalid`Указывает, `COleDateTimeSpan` что этот объект является недействительным; то есть, его значение может быть неправильным.

- `COleDateTimeSpan::null`Означает, `COleDateTimeSpan` что этот объект является нулевым, т.е. что для этого объекта не было поставлено значение. (Это "нулевой" в базе данных смысле "не имеет значения", в отличие от СЗ NULL.)

Статус `COleDateTimeSpan` объекта является недействительным в следующих случаях:

- Если этот объект испытал переполнение или недопоге во время `+=` `-=`операции арифметического назначения, а именно.

- Если недействительное значение было назначено этому объекту.

- Если статус этого объекта был явно установлен `SetStatus`на недействительное использование .

Для получения более подробной информации об операциях, которые могут привести статус к недействительным, [см. COleDateTimeSpan::оператор No, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan: Оператор , - .](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)

Для получения дополнительной информации `COleDateTimeSpan` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

## <a name="coledatetimespangettotaldays"></a><a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays

Получает эту дату/значение времени, выраженное в днях.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Эта дата/значение времени, выраженное в днях. Хотя эта функция является прототипом, чтобы вернуть двойник, она всегда будет возвращать значение integer.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются между приблизительно - 3.65e6 и 3.65e6.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

## <a name="coledatetimespangettotalhours"></a><a name="gettotalhours"></a>COleDateTimeSpan:GetTotalHours

Извлекает эту дату/значение времени, выраженное в часах.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Эта дата/значение времени, выраженное в часах. Хотя эта функция является прототипом, чтобы вернуть двойник, она всегда будет возвращать значение integer.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются между приблизительно - 8.77e7 и 8.77e7.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

Смотрите пример [GetTotalDays](#gettotaldays).

## <a name="coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes

Извлекает значение даты/пролет времени, выраженное в минутах.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Эта дата/значение времени, выраженное в минутах. Хотя эта функция является прототипом, чтобы вернуть двойник, она всегда будет возвращать значение integer.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются между приблизительно - 5.26e9 и 5.26e9.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

Смотрите пример [GetTotalDays](#gettotaldays).

## <a name="coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds

Извлекает значение даты/пролет времени, выраженное в секундах.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Значение этой даты/пролет времени выражается в секундах. Хотя эта функция является прототипом, чтобы вернуть двойник, она всегда будет возвращать значение integer.

### <a name="remarks"></a>Remarks

Значения возврата от этой функции варьируются от приблизительно - 3.16e11 до 3.16e11.

Для других функций, которые `COleDateTimeSpan` задавили значение объекта, см.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

### <a name="example"></a>Пример

Смотрите пример [GetTotalDays](#gettotaldays).

## <a name="coledatetimespanm_span"></a><a name="m_span"></a>COleDateTimeSpan::m_span

Базовое **двойное** значение `COleDateTime` для этого объекта.

```
double m_span;
```

### <a name="remarks"></a>Remarks

Это значение выражает дату/промежуток времени в днях.

> [!CAUTION]
> Изменение значения в члене **двойного** значения `COleDateTimeSpan` данных изменит значение этого объекта. Статус этого `COleDateTimeSpan` объекта не изменяется.

## <a name="coledatetimespanm_status"></a><a name="m_status"></a>COleDateTimeSpan::m_status

Типом для этого участника данных является `DateTimeSpanStatus`перечисленный тип, `COleDateTimeSpan` который определяется в классе.

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>Remarks

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Краткое описание этих значений статуса см.

- `COleDateTimeSpan::valid`Означает, `COleDateTimeSpan` что этот объект является действительным.

- `COleDateTimeSpan::invalid`Указывает, `COleDateTimeSpan` что этот объект является недействительным; то есть, его значение может быть неправильным.

- `COleDateTimeSpan::null`Означает, `COleDateTimeSpan` что этот объект является нулевым, т.е. что для этого объекта не было поставлено значение. (Это "нулевой" в базе данных смысле "не имеет значения", в отличие от СЗ NULL.)

Статус `COleDateTimeSpan` объекта является недействительным в следующих случаях:

- Если этот объект испытал переполнение или недопоге во время `+=` `-=`операции арифметического назначения, а именно.

- Если недействительное значение было назначено этому объекту.

- Если статус этого объекта был явно установлен на недействительным с помощью [SetStatus](#setstatus).

Для получения более подробной информации об операциях, которые могут привести статус к недействительным, [см. COleDateTimeSpan::оператор No, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan: Оператор , - .](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)

> [!CAUTION]
> Этот член данных предназначен для передовых ситуаций программирования. Вы должны использовать внеочередные функции членов [GetStatus](#getstatus) и [SetStatus.](#setstatus) Дополнительные предостережения читайте `SetStatus` в вопросе о явном настройке этого участника данных.

Для получения дополнительной информации `COleDateTimeSpan` о границах [Date and Time: Automation Support](../../atl-mfc-shared/date-and-time-automation-support.md)значений см.

## <a name="coledatetimespanoperator-"></a><a name="operator_eq"></a>COleDateTimeSpan::оператор

Копирует `COleDateTimeSpan` значение.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>Remarks

Этот перегруженный оператор назначения копирует значение исходной даты/пролет времени в этом `COleDateTimeSpan` объекте.

## <a name="coledatetimespanoperator---"></a><a name="operator_add_-"></a>COleDateTimeSpan::оператор, -

Добавление, вычитание и `COleDateTimeSpan` изменение знака для значений.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>Remarks

Первые два оператора позволяют добавлять и вычитать значения даты/пролет времени. Третий позволяет изменить значение даты/времени.

Если какая-либо из действий является нулевой, `COleDateTimeSpan` статус полученного значения является нулевым.

Если какая-либо из действий недействительна, а другая не `COleDateTimeSpan` является нулевой, статус полученного значения является недействительным.

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

## <a name="coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::оператор, --

Добавить и `COleDateTimeSpan` вычесть `COleDateTimeSpan` значение из этого значения.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Remarks

Эти операторы позволяют добавлять и вычитать значения `COleDateTimeSpan` даты/пролет времени из этого объекта. Если какая-либо из действий является нулевой, `COleDateTimeSpan` статус полученного значения является нулевым.

Если какая-либо из действий недействительна, а другая не `COleDateTimeSpan` является нулевой, статус полученного значения является недействительным.

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

## <a name="coledatetimespanoperator-double"></a><a name="operator_double"></a>COleDateTimeSpan:оператор двойной

Преобразует это `COleDateTimeSpan` значение в **двойное.**

```
operator double() const throw();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает значение `COleDateTimeSpan` этого значения в виде количества дней, плавающих точек.

## <a name="coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a>ColeDateTimeSpan::SetDateSpan

Устанавливает значение этой даты/значения времени.

```cpp
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Укажите значения даты и промежутка времени, `COleDateTimeSpan` которые будут скопированы в этот объект.

### <a name="remarks"></a>Remarks

Для функций, которые задавили значение `COleDateTimeSpan` объекта, см.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

## <a name="coledatetimespansetstatus"></a><a name="setstatus"></a>ColeDateTimeSpan::SetStatus

Устанавливает статус (действительность) `COleDateTimeSpan` этого объекта.

```cpp
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>Параметры

*status*<br/>
Новое значение статуса `COleDateTimeSpan` для этого объекта.

### <a name="remarks"></a>Remarks

Значение параметра *статуса* `DateTimeSpanStatus` определяется перечисленным типом, который `COleDateTimeSpan` определяется в классе.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Краткое описание этих значений статуса см.

- `COleDateTimeSpan::valid`Означает, `COleDateTimeSpan` что этот объект является действительным.

- `COleDateTimeSpan::invalid`Указывает, `COleDateTimeSpan` что этот объект является недействительным; то есть, его значение может быть неправильным.

- `COleDateTimeSpan::null`Означает, `COleDateTimeSpan` что этот объект является нулевым, т.е. что для этого объекта не было поставлено значение. (Это "нулевой" в базе данных смысле "не имеет значения", в отличие от СЗ NULL.)

   > [!CAUTION]
   > Эта функция предназначена для передовых ситуаций программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он будет использоваться для установки статуса **недействительным** или **недействительным.** Обратите внимание, что оператор назначения[(оператор )](#operator_eq)и [SetDateTimeSpan](#setdatetimespan) устанавливают состояние объекта на основе исходного значения (ы).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
