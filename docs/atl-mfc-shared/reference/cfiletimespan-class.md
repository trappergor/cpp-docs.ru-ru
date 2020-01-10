---
title: Класс CFileTimeSpan
ms.date: 01/06/2020
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
ms.openlocfilehash: 9220ed8373e78db727b43ecb59880dcfbcc98f96
ms.sourcegitcommit: 7bd3567fc6a0e7124aab51cad63bbdb44a99a848
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75755062"
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

Этот класс предоставляет методы для управления относительными периодами времени в единицах, используемых в файловой системе. Эти единицы часто используются в операциях, касающихся создания, последнего доступа или последнего изменения файла. Методы этого класса часто используются в сочетании с объектами [класса кфилетиме](../../atl-mfc-shared/reference/cfiletime-class.md) .

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
Период времени в миллисекундах.

### <a name="remarks"></a>Заметки

Объект `CFileTimeSpan` можно создать с помощью существующего объекта `CFileTimeSpan` или выражается как 64-разрядное значение. Конструктор по умолчанию задает интервал времени равным 0.

## <a name="gettimespan"></a>Кфилетимеспан:: TimeSpan

Вызовите этот метод для получения интервала времени из объекта `CFileTimeSpan`.

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает интервал времени в миллисекундах.

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
Новое значение интервала времени в единицах измерения 100-наносекундных. Дополнительные сведения см. в разделе [кфилетиме](cfiletime-class.md).

## <a name="see-also"></a>См. также:

\ [fileTime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)
\ [класса кфилетиме](cfiletime-class.md)
\ [диаграммы иерархии](../../mfc/hierarchy-chart.md)
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
