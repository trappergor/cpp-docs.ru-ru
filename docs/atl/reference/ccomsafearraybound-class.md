---
title: Класс CComSafeArrayBound
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
ms.openlocfilehash: 2c2f8b787e5366ec893538a88049f6f53dc35caf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327385"
---
# <a name="ccomsafearraybound-class"></a>Класс CComSafeArrayBound

Этот класс является оберткой для структуры [SAFEARRAYBOUND.](/windows/win32/api/oaidl/ns-oaidl-safearraybound)

## <a name="syntax"></a>Синтаксис

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|Конструктор.|
|[GetCount](#getcount)|Вызовите этот метод, чтобы вернуть количество элементов.|
|[GetLowerBound](#getlowerbound)|Вызовите этот метод, чтобы вернуть нижнюю границу.|
|[Getupperbound](#getupperbound)|Вызовите этот метод, чтобы вернуть верхнюю границу.|
|[SetCount](#setcount)|Вызовите этот метод, чтобы установить количество элементов.|
|[SetLowerBound](#setlowerbound)|Вызовите этот метод, чтобы установить нижнюю границу.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор](#operator_eq)|Устанавливает `CComSafeArrayBound` новое значение.|

## <a name="remarks"></a>Remarks

Этот класс является оберткой для структуры, используемой `SAFEARRAYBOUND` [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Он предоставляет методы для запроса и установки верхних и `CComSafeArray` нижних границ одного измерения объекта и количества элементов, которые он содержит. Многомерный `CComSafeArray` объект использует `CComSafeArrayBound` массив объектов, по одному для каждого измерения. Поэтому при использовании таких методов, как [GetCount,](#getcount)имейте в виду, что этот метод не вернет общее количество элементов в многомерном массиве.

**Заголовок:** atlsafe.h

## <a name="requirements"></a>Требования

**Заголовок:** atlsafe.h

## <a name="ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a>CComSafeArrayBound::CComSafeArrayBound

Конструктор.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Параметры

*ulCount*<br/>
Количество элементов в массиве.

*lLowerBound*<br/>
Нижняя граница, из которой пронумеророван массив.

### <a name="remarks"></a>Remarks

Если к массиву будет доступна программа СЗ, рекомендуется определить нижнюю границу как 0. Возможно, предпочтительнее использовать другое низкое значение, если массив будет использоваться с другими языками, такими как Visual Basic.

## <a name="ccomsafearrayboundgetcount"></a><a name="getcount"></a>CComSafeArrayBound::GetCount

Вызовите этот метод, чтобы вернуть количество элементов.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов.

### <a name="remarks"></a>Remarks

Если связанный `CComSafeArray` объект представляет собой многомерный массив, этот метод вернет только общее количество элементов в самом правом измерении. Используйте [CComSafeArray::GetCount,](../../atl/reference/ccomsafearray-class.md#getcount) чтобы получить общее количество элементов.

## <a name="ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a>CComSafeArrayBound::GetLowerBound

Вызовите этот метод, чтобы вернуть нижнюю границу.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает нижнюю границу `CComSafeArrayBound` объекта.

## <a name="ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a>CComSafeArrayBound::GetUpperBound

Вызовите этот метод, чтобы вернуть верхнюю границу.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верхнюю границу `CComSafeArrayBound` объекта.

### <a name="remarks"></a>Remarks

Верхняя граница зависит от количества элементов и нижнего значения. Например, если нижняя граница равня 0, а количество элементов — 10, верхняя граница автоматически устанавливается до 9.

## <a name="ccomsafearrayboundoperator-"></a><a name="operator_eq"></a>CComSafeArrayBound::оператор

Устанавливает `CComSafeArrayBound` новое значение.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Параметры

*привязка*<br/>
Объект `CComSafeArrayBound` .

*ulCount*<br/>
Число элементов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель объекту. `CComSafeArrayBound`

### <a name="remarks"></a>Remarks

Объект `CComSafeArrayBound` может быть назначен с `CComSafeArrayBound`помощью существующего или путем предоставления количества элементов, и в этом случае нижняя граница установлена на 0 по умолчанию.

## <a name="ccomsafearrayboundsetcount"></a><a name="setcount"></a>CComSafeArrayBound::SetCount

Вызовите этот метод, чтобы установить количество элементов.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Параметры

*ulCount*<br/>
Число элементов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов `CComSafeArrayBound` в объекте.

## <a name="ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a>CComSafeArrayBound::SetLowerBound

Вызовите этот метод, чтобы установить нижнюю границу.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Параметры

*lLowerBound*<br/>
Нижняя граница.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую нижнюю `CComSafeArrayBound` границу объекта.

### <a name="remarks"></a>Remarks

Если к массиву можно получить доступ из программы Visual C, рекомендуется определить нижнюю границу как 0. Возможно, предпочтительнее использовать другое низкое значение, если массив будет использоваться с другими языками, такими как Visual Basic.

Верхняя граница зависит от количества элементов и нижнего значения. Например, если нижняя граница равня 0, а количество элементов — 10, верхняя граница автоматически устанавливается до 9.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
