---
title: Класс Кфилетимеспан
ms.date: 10/18/2018
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
ms.openlocfilehash: f9bb42ba4c142f671a83dcfa7e99cff940fff047
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491290"
---
# <a name="cfiletimespan-class"></a>Класс Кфилетимеспан

Этот класс предоставляет методы для управления относительными значениями даты и времени, связанными с файлом.

## <a name="syntax"></a>Синтаксис

```
class CFileTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кфилетимеспан:: Кфилетимеспан](#cfiletimespan)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кфилетимеспан:: TimeSpan](#gettimespan)|Вызовите этот метод для получения интервала времени из `CFileTimeSpan` объекта.|
|[Кфилетимеспан:: Сеттимеспан](#settimespan)|Вызовите этот метод, чтобы задать интервал `CFileTimeSpan` времени объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Кфилетимеспан:: operator —](#operator_-)|Выполняет вычитание `CFileTimeSpan` объекта.|
|[Кфилетимеспан:: operator! =](#operator_neq)|Проверяет неравенство двух объектов `CFileTimeSpan`.|
|[Кфилетимеспан:: operator +](#operator_add)|Выполняет добавление `CFileTimeSpan` объекта.|
|[Кфилетимеспан:: operator + =](#operator_add_eq)|Выполняет добавление `CFileTimeSpan` объекта и присваивает результат текущему объекту.|
|[Кфилетимеспан:: operator&lt;](#operator_lt)|Сравнивает два `CFileTimeSpan` объекта, чтобы определить меньший.|
|[Кфилетимеспан:: operator&lt;=](#operator_lt_eq)|Сравнивает два `CFileTimeSpan` объекта, чтобы определить равенство или меньше.|
|[Кфилетимеспан:: operator =](#operator_eq)|Оператор присваивания.|
|[Кфилетимеспан:: operator-=](#operator_-_eq)|Выполняет вычитание `CFileTimeSpan` объекта и присваивает результат текущему объекту.|
|[Кфилетимеспан:: operator = =](#operator_eq_eq)|Сравнивает два объекта `CFileTimeSpan` на равенство.|
|[Кфилетимеспан:: operator&gt;](#operator_gt)|Сравнивает два `CFileTimeSpan` объекта для определения большего.|
|[Кфилетимеспан:: operator&gt;=](#operator_gt_eq)|Сравнивает два `CFileTimeSpan` объекта для определения равенства или большего.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для управления относительными периодами времени, часто встречающихся при выполнении операций, касающихся создания файла, последнего доступа или последнего изменения. Методы этого класса часто используются в сочетании с объектами [класса кфилетиме](../../atl-mfc-shared/reference/cfiletime-class.md) .

## <a name="example"></a>Пример

См. пример для [кфилетиме:: миллисекунд](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Требования

**Заголовок:** атлтиме. h

##  <a name="cfiletimespan"></a>Кфилетимеспан:: Кфилетимеспан

Конструктор.

```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Существующий объект `CFileTimeSpan`.

*нспан*<br/>
Период времени в миллисекундах.

### <a name="remarks"></a>Примечания

Объект можно создать с помощью существующего `CFileTimeSpan` объекта или выразить как 64-разрядное значение. `CFileTimeSpan` Конструктор по умолчанию задает интервал времени равным 0.

##  <a name="gettimespan"></a>Кфилетимеспан:: TimeSpan

Вызовите этот метод для получения интервала времени из `CFileTimeSpan` объекта.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает интервал времени в миллисекундах.

##  <a name="operator_-"></a>Кфилетимеспан:: operator —

Выполняет вычитание `CFileTimeSpan` объекта.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

`CFileTimeSpan` Возвращает объект, представляющий результат разности между двумя интервалами времени.

##  <a name="operator_neq"></a>Кфилетимеспан:: operator! =

Проверяет неравенство двух объектов `CFileTimeSpan`.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если сравниваемый элемент не равен `CFileTimeSpan` объекту; в противном случае — значение false.

##  <a name="operator_add"></a>Кфилетимеспан:: operator +

Выполняет добавление `CFileTimeSpan` объекта.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

`CFileTimeSpan` Возвращает объект, содержащий сумму двух интервалов времени.

##  <a name="operator_add_eq"></a>Кфилетимеспан:: operator + =

Выполняет добавление `CFileTimeSpan` объекта и присваивает результат текущему объекту.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объект, содержащий сумму двух интервалов времени.

##  <a name="operator_lt"></a>Кфилетимеспан:: operator&lt;

Сравнивает два `CFileTimeSpan` объекта, чтобы определить меньший.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше (т. е. представляет более короткий период времени), чем второй; в противном случае — значение FALSE.

##  <a name="operator_lt_eq"></a>Кфилетимеспан:: operator&lt;=

Сравнивает два `CFileTimeSpan` объекта, чтобы определить равенство или меньше.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше (т. е. представляет более короткий период времени) или равен второму, в противном случае — FALSE.

##  <a name="operator_eq"></a>Кфилетимеспан:: operator =

Оператор присваивания.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объект.

##  <a name="operator_-_eq"></a>Кфилетимеспан:: operator-=

Выполняет вычитание `CFileTimeSpan` объекта и присваивает результат текущему объекту.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объект.

##  <a name="operator_eq_eq"></a>Кфилетимеспан:: operator = =

Сравнивает два объекта `CFileTimeSpan` на равенство.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты равны; в противном случае — значение FALSE.

##  <a name="operator_gt"></a>Кфилетимеспан:: operator&gt;

Сравнивает два `CFileTimeSpan` объекта для определения большего.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше (т. е. представляет более длительный период времени), чем второй; в противном случае — значение FALSE.

##  <a name="operator_gt_eq"></a>Кфилетимеспан:: operator&gt;=

Сравнивает два `CFileTimeSpan` объекта для определения равенства или большего.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше (т. е. представляет более длительный период времени) или равен второму, в противном случае — FALSE.

##  <a name="settimespan"></a>Кфилетимеспан:: Сеттимеспан

Вызовите этот метод, чтобы задать интервал `CFileTimeSpan` времени объекта.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*нспан*<br/>
Новое значение интервала времени в миллисекундах.

## <a name="see-also"></a>См. также

[ЗНАЧЕНИЯ](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[Класс CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
