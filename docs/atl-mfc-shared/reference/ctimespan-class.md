---
title: Класс CTimeSpan
ms.date: 10/18/2018
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
ms.openlocfilehash: 14aa5eb52e2c631a92e40ae7053c566284e00e57
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317505"
---
# <a name="ctimespan-class"></a>Класс CTimeSpan

Количество времени, которое внутренне хранится как количество секунд в промежутке времени.

## <a name="syntax"></a>Синтаксис

```
class CTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTimeSpan:CTimeSpan](#ctimespan)|Строит `CTimeSpan` объекты различными способами.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTimeSpan::Формат](#format)|Преобразуется `CTimeSpan` в отформатированную строку.|
|[CTimeSpan::GetDays](#getdays)|Возвращает значение, представляющее количество полных `CTimeSpan`дней в этом.|
|[CTimeSpan::GetHours](#gethours)|Возвращает значение, которое представляет количество часов в текущем дне (-23 до 23).|
|[CTimeSpan::GetMinutes](#getminutes)|Возвращает значение, представляющее количество минут в текущем часе (-59 до 59).|
|[CTimeSpan::GetSeconds](#getseconds)|Возвращает значение, представляющее количество секунд в текущей минуте (-59 через 59).|
|[CTimeSpan:GetTimeSpan](#gettimespan)|Возвращает значение `CTimeSpan` объекта.|
|[CTimeSpan::GetTotalHours](#gettotalhours)|Возвращает значение, представляющее общее количество полных часов в этом. `CTimeSpan`|
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает значение, представляющее общее количество полных минут в этом. `CTimeSpan`|
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает значение, представляющее общее количество полных секунд в этом. `CTimeSpan`|
|[CTimeSpan::Serialize64](#serialize64)|Сериализирует данные в архив или из нее.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор - -](#operator_add_-)|Добавляет и вычитает объекты. `CTimeSpan`|
|[оператором --](#operator_add_eq_-_eq)|Добавляет и вычитает `CTimeSpan` объект и `CTimeSpan`из этого.|
|[оператор , < и т.д.](#ctimespan_comparison_operators)|Сравнивает два относительных значения времени.|

## <a name="remarks"></a>Remarks

`CTimeSpan`не имеет базового класса.

`CTimeSpan`функции преобразуют секунды в различные комбинации дней, часов, минут и секунд.

Объект `CTimeSpan` хранится в **__time64_t** структуре, которая составляет 8 байтов.

Класс компаньона, [CTime](../../atl-mfc-shared/reference/ctime-class.md), представляет собой абсолютное время.

И `CTime` `CTimeSpan` классы не предназначены для произвобовательных. Поскольку виртуальных функций нет, `CTime` `CTimeSpan` размер обоих объектов и объектов составляет ровно 8 байтов. Большинство функций членов являются внеочередными.

Для получения дополнительной `CTimeSpan`информации об использовании, [Time Management](../../c-runtime-library/time-management.md) *Run-Time Library Reference* [см.](../../atl-mfc-shared/date-and-time.md)

## <a name="requirements"></a>Требования

**Заголовок:** atltime.h

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a>Операторы сравнения CTimeSpan

Операторы сравнения.

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Эти операторы сравнивают два относительных значения времени. Они возвращаются true, если условие верно; в противном случае FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a>CTimeSpan:CTimeSpan

Строит `CTimeSpan` объекты различными способами.

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(
    LONG lDays,
    int nHours,
    int nMins,
    int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*timeSpanSrc*<br/>
Объект, `CTimeSpan` который уже существует.

*time*<br/>
Значение **__time64_t** времени, которое является числом секунд в промежутке времени.

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Дни, часы, минуты и секунды, соответственно.

### <a name="remarks"></a>Remarks

Все эти конструкторы создают `CTimeSpan` новый объект, инициализированный с указанным относительным временем. Каждый конструктор описан ниже:

- `CTimeSpan( );`Строит неначальный `CTimeSpan` объект.

- `CTimeSpan( const CTimeSpan& );`Строит `CTimeSpan` объект из `CTimeSpan` другого значения.

- `CTimeSpan( __time64_t );`Строит `CTimeSpan` объект из **__time64_t** типа.

- `CTimeSpan( LONG, int, int, int );`Строит `CTimeSpan` объект из компонентов, каждый компонент которых ограничен следующими диапазонами:

   |Компонент|Диапазон|
   |---------------|-----------|
   |*lDays*|0-25 000 (приблизительно)|
   |*nЧасы*|0-23|
   |*nMins*|0-59|
   |*nSecs*|0-59|

Обратите внимание, что версия Debug библиотеки класса Microsoft Foundation утверждает, что один или несколько компонентов времени находится вне диапазона. Вы несете ответственность за проверку аргументов до вызова.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a>CTimeSpan::Формат

Генерирует отформатированную строку, `CTimeSpan`соответствующую этому.

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Параметры

*pFormat*, *pszFormat*<br/>
Строка форматирования, `printf` похожая на строку форматирования. Коды форматирования, предшествующий знаку процента`%` `CTimeSpan` () заменяются соответствующим компонентом. Другие символы строки форматирования копируются без изменений в возвращенную строку. Значение и значение кодов форматирования `Format` для приведены ниже:

- **%D** Всего дней в этом`CTimeSpan`

- **%H** Часы в текущем дне

- **%M** Минуты в текущем часе

- **%S** Секунды в текущей минуте

- **%%** Процент наяпийк

*nID*<br/>
Идентификатор строки, идентифицирует этот формат.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий отформатированные время.

### <a name="remarks"></a>Remarks

Версия библиотеки Debug проверяет коды форматирования и утверждает, если код не находится в списке выше.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a>CTimeSpan::GetDays

Возвращает значение, представляющее количество полных `CTimeSpan`дней в этом.

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество полных 24-часовых дней в промежутке времени. Это значение может быть отрицательным, если промежуток времени отрицательный.

### <a name="remarks"></a>Remarks

Обратите внимание, что летнее время может привести `GetDays` к возвращению потенциально удивительный результат. Например, когда dST действует, `GetDays` сообщает количество дней между 1 апреля и 1 мая, как 29, а не 30, потому что один день в апреле сокращается на час и, следовательно, не считается полным днем.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a>CTimeSpan::GetHours

Возвращает значение, которое представляет количество часов в текущем дне (-23 до 23).

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество часов в текущем дне. Диапазон от -23 до 23.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a>CTimeSpan::GetMinutes

Возвращает значение, представляющее количество минут в текущем часе (-59 до 59).

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество минут в текущем часе. Диапазон от -59 до 59.

### <a name="example"></a>Пример

Смотрите пример [GetHours](#gethours).

## <a name="ctimespangetseconds"></a><a name="getseconds"></a>CTimeSpan::GetSeconds

Возвращает значение, представляющее количество секунд в текущей минуте (-59 через 59).

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество секунд в текущей минуте. Диапазон от -59 до 59.

### <a name="example"></a>Пример

Смотрите пример [GetHours](#gethours).

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a>CTimeSpan:GetTimeSpan

Возвращает значение `CTimeSpan` объекта.

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее `CTimeSpan` значение объекта.

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a>CTimeSpan::GetTotalHours

Возвращает значение, представляющее общее количество полных часов в этом. `CTimeSpan`

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает общее количество полных `CTimeSpan`часов в этом.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes

Возвращает значение, представляющее общее количество полных минут в этом. `CTimeSpan`

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает общее количество полных `CTimeSpan`минут в этом.

### <a name="example"></a>Пример

Смотрите пример [GetTotalHours](#gettotalhours).

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds

Возвращает значение, представляющее общее количество полных секунд в этом. `CTimeSpan`

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает общее количество полных `CTimeSpan`секунд в этом.

### <a name="example"></a>Пример

Смотрите пример [GetTotalHours](#gettotalhours).

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a>CTimeSpan::оператор, -

Добавляет и вычитает объекты. `CTimeSpan`

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Значение для добавления к объекту. `CTimeSpan`

### <a name="return-value"></a>Возвращаемое значение

Объект, `CTimeSpan` представляющий результат операции.

### <a name="remarks"></a>Remarks

Эти два оператора позволяют добавлять и вычесть `CTimeSpan` объекты друг другу и друг от друга.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>CTimeSpan::оператор, --

Добавляет и вычитает `CTimeSpan` объект и `CTimeSpan`из этого.

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Значение для добавления к объекту. `CTimeSpan`

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CTimeSpan` объект.

### <a name="remarks"></a>Remarks

Эти операторы позволяют добавлять `CTimeSpan` и вычесть `CTimeSpan`объект и из этого.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a>CTimeSpan::Serialize64

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

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
