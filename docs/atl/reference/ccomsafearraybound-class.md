---
title: Класс Ккомсафеаррайбаунд
ms.date: 05/06/2019
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
ms.openlocfilehash: 0386092ac26e71fcf5e840594a6b07f56cc9badd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739750"
---
# <a name="ccomsafearraybound-class"></a>Класс Ккомсафеаррайбаунд

Этот класс является оболочкой для структуры [сафеаррайбаунд](/windows/win32/api/oaidl/ns-oaidl-safearraybound) .

## <a name="syntax"></a>Синтаксис

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|Конструктор.|
|[GetCount](#getcount)|Вызовите этот метод, чтобы получить количество элементов.|
|[жетловербаунд](#getlowerbound)|Вызовите этот метод, чтобы вернуть нижнюю границу.|
|[GetUpperBound](#getupperbound)|Вызовите этот метод, чтобы получить верхнюю границу.|
|[сеткаунт](#setcount)|Вызовите этот метод, чтобы задать количество элементов.|
|[сетловербаунд](#setlowerbound)|Вызовите этот метод, чтобы задать нижнюю границу.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](#operator_eq)|`CComSafeArrayBound` Задает новое значение.|

## <a name="remarks"></a>Примечания

Этот класс является оболочкой для `SAFEARRAYBOUND` структуры, используемой [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Он предоставляет методы для запросов и установки верхних и нижних границ одного измерения `CComSafeArray` объекта и числа элементов, содержащихся в нем. В многомерном `CComSafeArray` объекте используется `CComSafeArrayBound` массив объектов, по одному для каждого измерения. Поэтому при использовании таких методов, как [NOCOUNT](#getcount), следует помнить, что этот метод не возвращает общее число элементов в многомерном массиве.

**Заголовок:** atlsafe.h

## <a name="requirements"></a>Требования

**Заголовок:** atlsafe.h

##  <a name="ccomsafearraybound"></a>Ккомсафеаррайбаунд:: Ккомсафеаррайбаунд

Конструктор.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Параметры

*улкаунт*<br/>
Количество элементов в массиве.

*лловербаунд*<br/>
Нижняя граница, с которой пронумерован массив.

### <a name="remarks"></a>Примечания

Если доступ к массиву осуществляется из C++ программы, рекомендуется, чтобы нижняя граница была определена как 0. Может быть предпочтительнее использовать другое значение нижней границы, если массив используется с другими языками, например Visual Basic.

##  <a name="getcount"></a>Ккомсафеаррайбаунд:: NOCOUNT

Вызовите этот метод, чтобы получить количество элементов.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов.

### <a name="remarks"></a>Примечания

Если связанный `CComSafeArray` объект представляет многомерный массив, этот метод возвратит только общее число элементов в крайнем правом измерении. Чтобы получить общее количество элементов, используйте [CComSafeArray:: NOCOUNT](../../atl/reference/ccomsafearray-class.md#getcount) .

##  <a name="getlowerbound"></a>Ккомсафеаррайбаунд:: Жетловербаунд

Вызовите этот метод, чтобы вернуть нижнюю границу.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает нижнюю границу `CComSafeArrayBound` объекта.

##  <a name="getupperbound"></a>Ккомсафеаррайбаунд:: GetUpperBound

Вызовите этот метод, чтобы получить верхнюю границу.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верхнюю границу `CComSafeArrayBound` объекта.

### <a name="remarks"></a>Примечания

Верхняя граница зависит от количества элементов и значения нижней границы. Например, если нижняя граница равна 0, а число элементов равно 10, то верхняя граница будет автоматически установлена в значение 9.

##  <a name="operator_eq"></a>Ккомсафеаррайбаунд:: operator =

`CComSafeArrayBound` Задает новое значение.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Параметры

*выход*<br/>
Объект `CComSafeArrayBound`.

*улкаунт*<br/>
Количество элементов

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `CComSafeArrayBound` объект.

### <a name="remarks"></a>Примечания

Объект может быть назначен с помощью существующего `CComSafeArrayBound`или путем предоставления количества элементов, в противном случае значение нижней границы по умолчанию равно 0. `CComSafeArrayBound`

##  <a name="setcount"></a>Ккомсафеаррайбаунд:: Сеткаунт

Вызовите этот метод, чтобы задать количество элементов.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Параметры

*улкаунт*<br/>
Количество элементов

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов в `CComSafeArrayBound` объекте.

##  <a name="setlowerbound"></a>Ккомсафеаррайбаунд:: Сетловербаунд

Вызовите этот метод, чтобы задать нижнюю границу.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Параметры

*лловербаунд*<br/>
Нижняя граница.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую нижнюю границу `CComSafeArrayBound` объекта.

### <a name="remarks"></a>Примечания

Если доступ к массиву осуществляется из визуальной C++ программы, рекомендуется, чтобы нижняя граница была определена как 0. Может быть предпочтительнее использовать другое значение нижней границы, если массив используется с другими языками, например Visual Basic.

Верхняя граница зависит от количества элементов и значения нижней границы. Например, если нижняя граница равна 0, а число элементов равно 10, то верхняя граница будет автоматически установлена в значение 9.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
