---
title: Класс CFileTimeSpan | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06a9f4275ff6acfcef7b7173fbfc6f9abf89b4f3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766010"
---
# <a name="cfiletimespan-class"></a>Класс CFileTimeSpan

Этот класс предоставляет методы для управления относительных дат и времени значения, связанные с файлом.

## <a name="syntax"></a>Синтаксис

```
class CFileTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Вызовите этот метод для получения интервал времени из `CFileTimeSpan` объекта.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Вызовите этот метод, чтобы задать временной период из `CFileTimeSpan` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CFileTimeSpan::operator-](#operator_-)|Выполняет вычитание на `CFileTimeSpan` объекта.|
|[CFileTimeSpan::operator! =](#operator_neq)|Проверяет неравенство двух объектов `CFileTimeSpan`.|
|[CFileTimeSpan::operator +](#operator_add)|Выполняет сложение `CFileTimeSpan` объекта.|
|[CFileTimeSpan::operator +=](#operator_add_eq)|Выполняет сложение `CFileTimeSpan` объекта и присвоить его результат в текущий объект.|
|[CFileTimeSpan::operator &lt;](#operator_lt)|Сравнивает два `CFileTimeSpan` объектов, чтобы определить меньший из них.|
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|Сравнивает два `CFileTimeSpan` объектов, чтобы определить равенство или меньший из них.|
|[CFileTimeSpan::operator =](#operator_eq)|Оператор присваивания.|
|[CFileTimeSpan::operator-=](#operator_-_eq)|Выполняет вычитание на `CFileTimeSpan` объекта и присвоить его результат в текущий объект.|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Сравнивает два объекта `CFileTimeSpan` на равенство.|
|[CFileTimeSpan::operator &gt;](#operator_gt)|Сравнивает два `CFileTimeSpan` объектов, чтобы определить больший.|
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|Сравнивает два `CFileTimeSpan` объектов, чтобы определить равенство или больший.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для управления относительный периоды времени, часто встречающихся при выполнении операций, определяя время создания, последнего доступа к или файла последнего изменения. Методы этого класса часто используются в сочетании с [класс CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md) объектов.

## <a name="example"></a>Пример

См. в примере [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Требования

**Заголовок:** atltime.h

##  <a name="cfiletimespan"></a>  CFileTimeSpan::CFileTimeSpan

Конструктор.

```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Существующий объект `CFileTimeSpan`.

*nSpan*  
Период времени в миллисекундах.

### <a name="remarks"></a>Примечания

`CFileTimeSpan` Объект может быть создан с помощью существующего `CFileTimeSpan` объекта или выраженный 64-разрядное значение. Конструктор по умолчанию задает промежуток времени, равным 0.

##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan

Вызовите этот метод для получения интервал времени из `CFileTimeSpan` объекта.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает интервал времени в миллисекундах.

##  <a name="operator_-"></a>  CFileTimeSpan::operator-

Выполняет вычитание на `CFileTimeSpan` объекта.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTimeSpan` объект, представляющий результат разницу между двумя промежутками времени.

##  <a name="operator_neq"></a>  CFileTimeSpan::operator! =

Проверяет неравенство двух объектов `CFileTimeSpan`.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент с которым производится сравнение не равно `CFileTimeSpan` объекта; в противном случае — FALSE.

##  <a name="operator_add"></a>  CFileTimeSpan::operator +

Выполняет сложение `CFileTimeSpan` объекта.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTimeSpan` объект, содержащий сумму два временных диапазонов.

##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator +=

Выполняет сложение на `CFileTimeSpan` объект и присваивает результат текущему объекту.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объект, содержащий сумму два временных диапазонов.

##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;

Сравнивает два `CFileTimeSpan` объектов, чтобы определить меньший из них.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше (то есть представляет более короткий период времени) второго, в противном случае — значение FALSE.

##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=

Сравнивает два `CFileTimeSpan` объектов, чтобы определить равенство или меньший из них.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше (то есть представляет более короткий период времени) или равен ему, в противном случае — значение FALSE.

##  <a name="operator_eq"></a>  CFileTimeSpan::operator =

Оператор присваивания.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объекта.

##  <a name="operator_-_eq"></a>  CFileTimeSpan::operator-=

Выполняет вычитание на `CFileTimeSpan` объект и присваивает результат текущему объекту.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объекта.

##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator ==

Сравнивает два объекта `CFileTimeSpan` на равенство.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты равны, в противном случае — значение FALSE.

##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;

Сравнивает два `CFileTimeSpan` объектов, чтобы определить больший.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше, чем (то есть представляет более длительный период времени) второго, в противном случае — значение FALSE.

##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=

Сравнивает два `CFileTimeSpan` объектов, чтобы определить равенство или больший.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*диапазон*  
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше, чем (то есть представляет более длительный период времени) или равен ему, в противном случае — значение FALSE.

##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan

Вызовите этот метод, чтобы задать временной период из `CFileTimeSpan` объекта.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*nSpan*  
Новое значение для диапазона времени в миллисекундах.

## <a name="see-also"></a>См. также

[FILETIME](https://msdn.microsoft.com/library/windows/desktop/ms724284)   
[Класс CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)   
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)

