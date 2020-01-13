---
title: Класс CFileTimeSpan
description: Класс Кфилетимеспан библиотеки ATL и Microsoft Foundation Classes (MFC) управляет интервалами времени в единицах FILETIME.
ms.date: 01/10/2020
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
ms.openlocfilehash: 89d95759b11ff7e52c2a8fa75cf94f7b7b81fa36
ms.sourcegitcommit: c3283062ce4e382aec7f11626d358a37caf8cdbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2020
ms.locfileid: "75914381"
---
# <a name="cfiletimespan-class"></a>Класс CFileTimeSpan

Этот класс предоставляет методы для управления относительными значениями даты и времени, связанными с файлом.

## <a name="syntax"></a>Синтаксис

```cpp
class CFileTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Name|Описание|
|----------|-----------------|
|[Кфилетимеспан:: Кфилетимеспан](#cfiletimespan)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Name|Описание|
|----------|-----------------|
|[Кфилетимеспан:: TimeSpan](#gettimespan)|Вызовите этот метод для получения интервала времени из объекта `CFileTimeSpan`.|
|[Кфилетимеспан:: Сеттимеспан](#settimespan)|Вызовите этот метод, чтобы задать интервал времени для объекта `CFileTimeSpan`.|

### <a name="public-operators"></a>Открытые операторы

|Name|Описание|
|----------|-----------------|
|[Кфилетимеспан:: operator —](#operator_-)|Выполняет вычитание для объекта `CFileTimeSpan`.|
|[Кфилетимеспан:: operator! =](#operator_neq)|Проверяет неравенство двух объектов `CFileTimeSpan`.|
|[Кфилетимеспан:: operator +](#operator_add)|Выполняет Добавление объекта `CFileTimeSpan`.|
|[Кфилетимеспан:: operator + =](#operator_add_eq)|Выполняет Добавление объекта `CFileTimeSpan` и присваивает результат текущему объекту.|
|[Кфилетимеспан:: operator &lt;](#operator_lt)|Сравнивает два `CFileTimeSpan` объектов для определения меньшего.|
|[Кфилетимеспан:: operator &lt;=](#operator_lt_eq)|Сравнивает два `CFileTimeSpan` объектов для определения равенства или меньшего.|
|[Кфилетимеспан:: operator =](#operator_eq)|Оператор присваивания.|
|[Кфилетимеспан:: operator-=](#operator_-_eq)|Выполняет вычитание объекта `CFileTimeSpan` и присваивает результат текущему объекту.|
|[Кфилетимеспан:: operator = =](#operator_eq_eq)|Сравнивает два объекта `CFileTimeSpan` на равенство.|
|[Кфилетимеспан:: operator &gt;](#operator_gt)|Сравнивает два `CFileTimeSpan` объектов для определения большего.|
|[Кфилетимеспан:: operator &gt;=](#operator_gt_eq)|Сравнивает два `CFileTimeSpan` объектов для определения равенства или большего.|

## <a name="remarks"></a>Заметки

Класс `CFileTimeSpan` предоставляет методы для управления относительными периодами времени в единицах, используемых в файловой системе. Эти единицы часто используются в операциях с файлами, например при создании файла, последнем доступе или при последнем изменении. Методы этого класса часто используются в сочетании с объектами [класса кфилетиме](../../atl-mfc-shared/reference/cfiletime-class.md) .

## <a name="example"></a>Пример

См. пример для [кфилетиме:: миллисекунд](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Требования

**Заголовок:** атлтиме. h

## <a name="cfiletimespan"></a>Кфилетимеспан:: Кфилетимеспан

Конструктор.

```cpp
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Существующий объект `CFileTimeSpan`.

*нспан*\
Период времени в единицах FILETIME.

### <a name="remarks"></a>Заметки

Объект `CFileTimeSpan` можно создать с помощью существующего объекта `CFileTimeSpan` или в виде 64-разрядного значения в единицах FILETIME в 100-наносекундных. Дополнительные сведения см. в разделе [кфилетиме](cfiletime-class.md). Конструктор по умолчанию задает интервал времени равным 0.

## <a name="gettimespan"></a>Кфилетимеспан:: TimeSpan

Вызовите этот метод для получения интервала времени из объекта `CFileTimeSpan`.

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает интервал времени в 100-наносекундных единицах FILETIME. Дополнительные сведения см. в разделе [кфилетиме](cfiletime-class.md).

## <a name="operator_-"></a>Кфилетимеспан:: operator —

Выполняет вычитание для объекта `CFileTimeSpan`.

```cpp
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект `CFileTimeSpan`, представляющий результат разности между двумя интервалами времени.

## <a name="operator_neq"></a>Кфилетимеспан:: operator! =

Проверяет неравенство двух объектов `CFileTimeSpan`.

```cpp
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если сравниваемый элемент не равен объекту `CFileTimeSpan`; в противном случае — FALSE.

## <a name="operator_add"></a>Кфилетимеспан:: operator +

Выполняет Добавление объекта `CFileTimeSpan`.

```cpp
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект `CFileTimeSpan`, содержащий сумму двух интервалов времени.

## <a name="operator_add_eq"></a>Кфилетимеспан:: operator + =

Выполняет Добавление объекта `CFileTimeSpan` и присваивает результат текущему объекту.

```cpp
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный объект `CFileTimeSpan`, содержащий сумму двух интервалов времени.

## <a name="operator_lt"></a>Кфилетимеспан:: operator &lt;

Сравнивает два `CFileTimeSpan` объектов для определения меньшего.

```cpp
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше (т. е. представляет более короткий период времени), чем второй; в противном случае — значение FALSE.

## <a name="operator_lt_eq"></a>Кфилетимеспан:: operator &lt;=

Сравнивает два `CFileTimeSpan` объектов для определения равенства или меньшего.

```cpp
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше (т. е. представляет более короткий период времени) или равен второму, в противном случае — FALSE.

## <a name="operator_eq"></a>Кфилетимеспан:: operator =

Оператор присваивания.

```cpp
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный объект `CFileTimeSpan`.

## <a name="operator_-_eq"></a>Кфилетимеспан:: operator-=

Выполняет вычитание объекта `CFileTimeSpan` и присваивает результат текущему объекту.

```cpp
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный объект `CFileTimeSpan`.

## <a name="operator_eq_eq"></a>Кфилетимеспан:: operator = =

Сравнивает два объекта `CFileTimeSpan` на равенство.

```cpp
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты равны; в противном случае — значение FALSE.

## <a name="operator_gt"></a>Кфилетимеспан:: operator &gt;

Сравнивает два `CFileTimeSpan` объектов для определения большего.

```cpp
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше (т. е. представляет более длительный период времени), чем второй; в противном случае — значение FALSE.

## <a name="operator_gt_eq"></a>Кфилетимеспан:: operator &gt;=

Сравнивает два `CFileTimeSpan` объектов для определения равенства или большего.

```cpp
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*охват*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше (т. е. представляет более длительный период времени) или равен второму, в противном случае — FALSE.

## <a name="settimespan"></a>Кфилетимеспан:: Сеттимеспан

Вызовите этот метод, чтобы задать интервал времени для объекта `CFileTimeSpan`.

```cpp
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*нспан*\
Новое значение для интервала времени в 100-наносекундных единицах FILETIME. Дополнительные сведения см. в разделе [кфилетиме](cfiletime-class.md).

## <a name="see-also"></a>См. также:

\ [fileTime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)
\ [класса кфилетиме](cfiletime-class.md)
\ [диаграммы иерархии](../../mfc/hierarchy-chart.md)
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
