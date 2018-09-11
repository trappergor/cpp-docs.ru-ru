---
title: Класс COleDateTimeSpan | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ee7ccca718a05529e5ebc88bccc7d23d258810c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758366"
---
# <a name="coledatetimespan-class"></a>Класс COleDateTimeSpan

Представляет относительное время, период времени.

## <a name="syntax"></a>Синтаксис

```
class COleDateTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Создает объект `COleDateTimeSpan`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDateTimeSpan::Format](#format)|Создает форматированное строковое представление `COleDateTimeSpan` объекта.|
|[COleDateTimeSpan::GetDays](#getdays)|Возвращает день часть диапазона, это `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::GetHours](#gethours)|Возвращает час часть диапазона, это `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::GetMinutes](#getminutes)|Возвращает часть диапазона `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::GetSeconds](#getseconds)|Возвращает во второй части диапазона `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::GetStatus](#getstatus)|Получает состояние (действия) это `COleDateTimeSpan` объекта.|
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Возвращает число дней, это `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Возвращает количество часов, это `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает количество минут, это `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает количество секунд, данный `COleDateTimeSpan` представляет объект.|
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Задает значение данного объекта `COleDateTimeSpan` объекта.|
|[COleDateTimeSpan::SetStatus](#setstatus)|Задает состояние (действия) это `COleDateTimeSpan` объекта.|

### <a name="public-operators"></a>Открытые операторы

|||
|-|-|
|[оператор +, -](#operator_add_-)|Добавить, вычесть, а также изменить входа для `COleDateTimeSpan` значения.|
|[оператор +=-=](#operator_add_eq_-_eq)|Добавление и вычитание `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значение.|
|[оператор =](#operator_eq)|Копирует `COleDateTimeSpan` значение.|
|[оператор ==, <, < =](#coledatetimespan_relational_operators)|Сравнение двух `COleDateTimeSpan` значения.|
|[double-оператор](#operator_double)|Преобразует данную `COleDateTimeSpan` значение **двойные**.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleDateTimeSpan::m_span](#m_span)|Содержит базовый **двойные** для данного `COleDateTimeSpan` объекта.|
|[COleDateTimeSpan::m_status](#m_status)|Содержит состояние данного объекта `COleDateTimeSpan` объекта.|

## <a name="remarks"></a>Примечания

`COleDateTimeSpan` не имеет базового класса.

Объект `COleDateTimeSpan` отслеживает время в днях.

`COleDateTimeSpan` используется с его вспомогательный класс [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime` Инкапсулирует `DATE` тип данных OLE-автоматизации. `COleDateTime` Представляет абсолютные значения времени. Все `COleDateTime` вычислений включают в себя `COleDateTimeSpan` значения. Отношение между этими классами является аналогом между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Дополнительные сведения о `COleDateTime` и `COleDateTimeSpan` классов, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Требования

**Заголовок:** ATLComTime.h

##  <a name="coledatetimespan_relational_operators"></a>  Операторы отношения COleDateTimeSpan

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

*dateSpan*  
Сравниваемый шаблон `COleDateTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Эти операторы сравнивают два значения интервала даты/времени и возвращает значение TRUE, если условие равно true; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  ATLASSERT возникнет в том случае, если один из операндов является недопустимым.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

##  <a name="coledatetimespan"></a>  COleDateTimeSpan::COleDateTimeSpan

Создает объект `COleDateTimeSpan`.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*dblSpanSrc*  
Число дней, который необходимо скопировать в новый `COleDateTimeSpan` объекта.

*lDays*, *nHours*, *nMins*, *nSecs*  
Значения дней недели и времени, который необходимо скопировать в новый `COleDateTimeSpan` объекта.

### <a name="remarks"></a>Примечания

Все эти конструкторы создают новые `COleDateTimeSpan` объекты, инициализированные указанное значение. Краткое описание каждого из этих конструкторов выглядит следующим образом:

- **() COleDateTimeSpan** создает `COleDateTimeSpan` объект инициализируется значением 0.

- **COleDateTimeSpan (** `dblSpanSrc` **)** создает `COleDateTimeSpan` объекта из значения с плавающей запятой.

- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)**  Создает `COleDateTimeSpan` объект инициализирован указанные числовые значения.

Состояние нового `COleDateTimeSpan` настроен на допустимый объект.

Дополнительные сведения о граничные значения для `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

##  <a name="format"></a>  COleDateTimeSpan::Format

Создает форматированное строковое представление `COleDateTimeSpan` объекта.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Параметры

*pFormat*  
Форматирование строки аналогичную `printf` форматирования строки. Коды, предшествует процента форматирования (`%`) выполните вход, заменен соответствующим `COleDateTimeSpan` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Значение и значение коды форматирования для `Format` , перечислены ниже:

- **%H** часов в текущей даты

- **%M** минут в текущий час

- **%S** секунд в текущую минуту

- **%%** Знак процента

Четыре коды формата, перечисленных выше приведены только коды, которые будет принимать формат.

-

*nID*  
Идентификатор ресурса для управления форматом строки.

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащее форматированное значение интервала даты/времени.

### <a name="remarks"></a>Примечания

Вызовите эти функции, чтобы создать форматированное представление значения интервала времени. Если состояние данного объекта `COleDateTimeSpan` объект имеет значение null, возвращаемое значение является пустой строкой. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс IDS_INVALID_DATETIMESPAN.

Краткое описание формы для этой функции выглядит следующим образом:

**Формат (** *pFormat* **)**  
Эта форма форматирует значение, используя строку формата, содержащий специальные коды форматирования, которым предшествует знак процента (%), как показано на `printf`. Строка форматирования передается в качестве параметра функции.

**Формат (** *nID* **)**  
Эта форма форматирует значение, используя строку формата, содержащий специальные коды форматирования, которым предшествует знак процента (%), как показано на `printf`. Строка форматирования — это ресурс. Идентификатор этого ресурса строка передается в качестве параметра.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

##  <a name="getdays"></a>  COleDateTimeSpan::GetDays

Извлекает сведения о дате этого значения интервала даты/времени.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть дня это значение интервала даты/времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этого диапазона функции между приблизительно - 3,615,000 и 3,615,000.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

##  <a name="gethours"></a>  COleDateTimeSpan::GetHours

Возвращает час из этого значения интервала даты/времени.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть часов это значение интервала даты/времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этого диапазона функции диапазоне от - 23 до 23.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetDays](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

##  <a name="getminutes"></a>  COleDateTimeSpan::GetMinutes

Извлекает часть это значение интервала даты/времени.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть минут это значение интервала даты/времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этого диапазона функции диапазоне от - 59 до 59.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

##  <a name="getseconds"></a>  COleDateTimeSpan::GetSeconds

Извлекает во второй части это значение интервала даты/времени.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть секунд в это значение интервала даты/времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этого диапазона функции диапазоне от - 59 до 59.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

##  <a name="getstatus"></a>  COleDateTimeSpan::GetStatus

Получает состояние (действия) это `COleDateTimeSpan` объекта.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние данного объекта `COleDateTimeSpan` значение.

### <a name="remarks"></a>Примечания

Возвращаемое значение определяется `DateTimeSpanStatus` перечислимый тип, который определен в `COleDateTimeSpan` класса.

```
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
};  
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleDateTimeSpan::valid` Указывает, что этот `COleDateTimeSpan` объект является допустимым.

- `COleDateTimeSpan::invalid` Указывает, что этот `COleDateTimeSpan` объекта является недопустимым; то есть его значение может быть неправильным.

- `COleDateTimeSpan::null` Указывает, что этот `COleDateTimeSpan` объект имеет значение null, то есть, что значение не указано для этого объекта. (Это «null» в смысле «предложений having без значения,» в отличие от C++ NULL базы данных.)

Состояние `COleDateTimeSpan` становится недействительным в следующих случаях:

- Если этот объект опыт работы с переполнения или потери значимости во время назначения, арифметические операции, а именно, `+=` или `-=`.

- Если недопустимое значение был назначен этот объект.

- Если состояние этого объекта было задано явно недопустимыми с помощью `SetStatus`.

Дополнительные сведения об операциях, которые может задать состояние на недопустимый см. в разделе [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

Дополнительные сведения о граничные значения для `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="gettotaldays"></a>  COleDateTimeSpan::GetTotalDays

Извлекает значение интервала даты/времени в днях.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение интервала даты/времени, в днях. Несмотря на то, что эта функция является прототипом для возврата типа double, оно всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этого диапазона функции между приблизительно - 3.65e6 и 3.65e6.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

##  <a name="gettotalhours"></a>  COleDateTimeSpan::GetTotalHours

Извлекает значение интервала даты/времени в часах.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение интервала даты/времени, в часах. Несмотря на то, что эта функция является прототипом для возврата типа double, оно всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этого диапазона функции между приблизительно - 8.77e7 и 8.77e7.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

См. в примере [GetTotalDays](#gettotaldays).

##  <a name="gettotalminutes"></a>  COleDateTimeSpan::GetTotalMinutes

Получает это значение интервала даты/времени, выраженный в минутах.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение интервала даты/времени, выраженный в минутах. Несмотря на то, что эта функция является прототипом для возврата типа double, оно всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этого диапазона функции между приблизительно - 5.26e9 и 5.26e9.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Пример

См. в примере [GetTotalDays](#gettotaldays).

##  <a name="gettotalseconds"></a>  COleDateTimeSpan::GetTotalSeconds

Получает это значение интервала даты/времени, выраженный в секундах.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение интервала даты/времени, выраженный в секундах. Несмотря на то, что эта функция является прототипом для возврата типа double, оно всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции в диапазоне от приблизительно - 3.16e11 для 3.16e11.

Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

### <a name="example"></a>Пример

См. в примере [GetTotalDays](#gettotaldays).

##  <a name="m_span"></a>  COleDateTimeSpan::m_span

Базовый **двойные** значение для данного `COleDateTime` объекта.

```
double m_span;
```

### <a name="remarks"></a>Примечания

Это значение указывает дату или интервал времени в днях.

> [!CAUTION]
>  Изменение значения в **двойные** элемента данных изменится значение этой `COleDateTimeSpan` объекта. Это не приводит к изменению состояния этого `COleDateTimeSpan` объекта.

##  <a name="m_status"></a>  COleDateTimeSpan::m_status

Перечислимый тип принадлежит к типу этого элемента данных `DateTimeSpanStatus`, который определен в `COleDateTimeSpan` класса.

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>Примечания

```
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleDateTimeSpan::valid` Указывает, что этот `COleDateTimeSpan` объект является допустимым.

- `COleDateTimeSpan::invalid` Указывает, что этот `COleDateTimeSpan` объекта является недопустимым; то есть его значение может быть неправильным.

- `COleDateTimeSpan::null` Указывает, что этот `COleDateTimeSpan` объект имеет значение null, то есть, что значение не указано для этого объекта. (Это «null» в смысле «предложений having без значения,» в отличие от C++ NULL базы данных.)

Состояние `COleDateTimeSpan` становится недействительным в следующих случаях:

- Если этот объект опыт работы с переполнения или потери значимости во время назначения, арифметические операции, а именно, `+=` или `-=`.

- Если недопустимое значение был назначен этот объект.

- Если состояние этого объекта было задано явно недопустимыми с помощью [SetStatus](#setstatus).

Дополнительные сведения об операциях, которые может задать состояние на недопустимый см. в разделе [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

> [!CAUTION]
>  Этот член данных — для сложных ситуациях программирования. Следует использовать подставляемые функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). См. в разделе `SetStatus` дополнительные предупреждения, касающиеся явного задания для этого элемента данных.

Дополнительные сведения о граничные значения для `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_eq"></a>  COleDateTimeSpan::operator =

Копирует `COleDateTimeSpan` значение.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>Примечания

Этот оператор назначения перегруженных копирует исходное значение интервала даты/времени в этот `COleDateTimeSpan` объекта.

##  <a name="operator_add_-"></a>  COleDateTimeSpan::operator +, -

Добавить, вычесть, а также изменить входа для `COleDateTimeSpan` значения.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>Примечания

Первые два операторы позволяют сложения и вычитания значения интервала даты/времени. Третий позволяет изменить знак значения интервала даты/времени.

Если любой из операндов имеет значение null, состояние результата `COleDateTimeSpan` имеет значение null.

Если любой из операндов является недопустимым, и другой не равно null, состояние результата `COleDateTimeSpan` недопустимое значение.

Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  COleDateTimeSpan::operator +=-=

Добавление и вычитание `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значение.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Примечания

Эти операторы позволяют сложения и вычитания значения интервала даты/времени из этого `COleDateTimeSpan` объекта. Если любой из операндов имеет значение null, состояние результата `COleDateTimeSpan` имеет значение null.

Если любой из операндов является недопустимым, и другой не равно null, состояние результата `COleDateTimeSpan` недопустимое значение.

Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

##  <a name="operator_double"></a>  COleDateTimeSpan::operator double

Преобразует данную `COleDateTimeSpan` значение **двойные**.

```
operator double() const throw();
```

### <a name="remarks"></a>Примечания

Этот оператор возвращает значение этой `COleDateTimeSpan` значение с плавающей запятой количество дней.

##  <a name="setdatetimespan"></a>  COleDateTimeSpan::SetDateTimeSpan

Задает значение этого интервала даты/времени значения.

```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*lDays*, *nHours*, *nMins*, *nSecs*  
Значения в диапазоне дат и времени копируются в это `COleDateTimeSpan` объекта.

### <a name="remarks"></a>Примечания

Для функций, которые запроса значения `COleDateTimeSpan` объекта, см. в разделе следующих функций-членов:

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

##  <a name="setstatus"></a>  COleDateTimeSpan::SetStatus

Задает состояние (действия) это `COleDateTimeSpan` объекта.

```
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>Параметры

*status*  
Новое значение состояния для данного `COleDateTimeSpan` объекта.

### <a name="remarks"></a>Примечания

*Состояние* значение параметра определяется `DateTimeSpanStatus` перечислимый тип, который определен в `COleDateTimeSpan` класса.

```
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleDateTimeSpan::valid` Указывает, что этот `COleDateTimeSpan` объект является допустимым.

- `COleDateTimeSpan::invalid` Указывает, что этот `COleDateTimeSpan` объекта является недопустимым; то есть его значение может быть неправильным.

- `COleDateTimeSpan::null` Указывает, что этот `COleDateTimeSpan` объект имеет значение null, то есть, что значение не указано для этого объекта. (Это «null» в смысле «предложений having без значения,» в отличие от C++ NULL базы данных.)

   > [!CAUTION]
   > Эта функция служит для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего будет использоваться для задания состояния **null** или **недопустимый**. Обратите внимание, что оператор присваивания ( [оператор =](#eq)) и [SetDateTimeSpan](#setdatetimespan) задать состояние объекта на основании значения источника.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>См. также

[Класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)   
[Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)   
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)

