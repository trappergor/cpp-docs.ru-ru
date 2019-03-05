---
title: Класс CComSafeArray
ms.date: 11/04/2016
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
ms.openlocfilehash: 0262764c950b01acdb610873a995a9a6fd912997
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280684"
---
# <a name="ccomsafearray-class"></a>Класс CComSafeArray

Этот класс является оболочкой для `SAFEARRAY` структуры.

## <a name="syntax"></a>Синтаксис

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных для сохранения в массиве.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Конструктор.|
|[CComSafeArray:: ~ CComSafeArray](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CComSafeArray::Add](#add)|Добавляет один или несколько элементов, или `SAFEARRAY` структуру `CComSafeArray`.|
|[CComSafeArray::Attach](#attach)|Присоединяет `SAFEARRAY` структуру `CComSafeArray` объекта.|
|[CComSafeArray::CopyFrom](#copyfrom)|Копирует содержимое объекта `SAFEARRAY` структуры в `CComSafeArray` объекта.|
|[CComSafeArray::CopyTo](#copyto)|Создает копию объекта `CComSafeArray`.|
|[CComSafeArray::Create](#create)|Создает объект `CComSafeArray`.|
|[CComSafeArray::Destroy](#destroy)|Уничтожает объект `CComSafeArray`.|
|[CComSafeArray::Detach](#detach)|Отсоединяет `SAFEARRAY` из `CComSafeArray` объекта.|
|[CComSafeArray::GetAt](#getat)|Получает один элемент из одномерного массива.|
|[CComSafeArray::GetCount](#getcount)|Возвращает число элементов в массиве.|
|[CComSafeArray::GetDimensions](#getdimensions)|Возвращает число измерений в массиве.|
|[CComSafeArray::GetLowerBound](#getlowerbound)|Возвращает нижнюю границу заданного измерения массива.|
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Возвращает адрес элемента данных `m_psa` .|
|[CComSafeArray::GetType](#gettype)|Возвращает тип данных, хранящихся в массиве.|
|[CComSafeArray::GetUpperBound](#getupperbound)|Возвращает верхнюю границу любого измерения массива.|
|[CComSafeArray::IsSizable](#issizable)|Проверяет, можно ли изменить размер объекта `CComSafeArray` .|
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|Получает один элемент из многомерного массива.|
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|Задает значение элемента в многомерном массиве.|
|[CComSafeArray::Resize](#resize)|Изменяет размер объекта `CComSafeArray` .|
|[CComSafeArray::SetAt](#setat)|Задает значение элемента в одномерном массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|Приводит значение к `SAFEARRAY` указатель.|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Получает элемент из массива.|
|[CComSafeArray::operator =](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComSafeArray::m_psa](#m_psa)|Этот элемент данных содержит адрес `SAFEARRAY` структуры.|

## <a name="remarks"></a>Примечания

`CComSafeArray` предоставляет оболочку для класса [SAFEARRAY Data Type](/windows/desktop/api/oaidl/ns-oaidl-tagsafearray) , упрощая создание одно- и многомерных массивов практически любого поддерживаемого типа VARIANT и управление ими.

`CComSafeArray` упрощает передачу массивов между процессами и обеспечивает дополнительную безопасность путем проверки значений индекса массива на соответствие верхней и нижней границам.

Нижняя граница `CComSafeArray` может начинаться с любого определенного пользователем значения. Однако нижняя граница массивов, доступ к которым осуществляется через C++, должна быть равна 0. В других языках, например Visual Basic, могут использоваться другие ограничивающие значения (например, от −10 до 10).

Используйте [CComSafeArray::Create](#create) для создания объекта `CComSafeArray` , и [CComSafeArray::Destroy](#destroy) — для его удаления.

`CComSafeArray` может содержать следующее подмножество типов данных VARIANT.

|VARTYPE|Описание|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|указатель типа decimal|
|VT_VARIANT|указатель типа variant|
|VT_CY|Currency - тип данных|

## <a name="requirements"></a>Требования

**Заголовок:** atlsafe.h

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

##  <a name="add"></a>  CComSafeArray::Add

Добавляет один или несколько элементов, или `SAFEARRAY` структуру `CComSafeArray`.

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Параметры

*psaSrc*<br/>
Указатель на объект `SAFEARRAY` .

*Инициализирует метод ulCount*<br/>
Количество объектов, добавляемых в массив.

*pT*<br/>
Указатель на один или несколько объектов, добавляемый в массив.

*t*<br/>
Ссылка на объект, добавляемый в массив.

*bCopy*<br/>
Указывает, следует ли создавать копию данных. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Новые объекты добавляются в конец существующего `SAFEARRAY` объекта. При добавлении объекта многомерный массив `SAFEARRAY` объект не поддерживается. При добавлении существующего массива объектов, обоих массивов может содержать элементы того же типа.

*BCopy* флаг учитывается при добавлении элементов типа BSTR и VARIANT в массив. Значение по умолчанию TRUE гарантирует, что новая копия состоит из данных, при добавлении элемента в массиве.

##  <a name="attach"></a>  CComSafeArray::Attach

Присоединяет `SAFEARRAY` структуру `CComSafeArray` объекта.

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*psaSrc*<br/>
Указатель на `SAFEARRAY` структуры.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Присоединяет `SAFEARRAY` структуру `CComSafeArray` объекта, делая существующий `CComSafeArray` доступные методы.

##  <a name="ccomsafearray"></a>  CComSafeArray::CComSafeArray

Конструктор.

```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*привязан*<br/>
Структура `SAFEARRAYBOUND`.

*Инициализирует метод ulCount*<br/>
Количество элементов в массиве.

*lLBound*<br/>
Значение нижней границы; то есть индекс первого элемента в массиве.

*pBound*<br/>
Указатель на `SAFEARRAYBOUND` структуры.

*uDims*<br/>
Число измерений в массиве.

*saSrc*<br/>
Ссылку на `SAFEARRAY` структуры или `CComSafeArray` объекта. В любом случае конструктор использует эту ссылку для создания копии массива, поэтому после создания не используется массив.

*psaSrc*<br/>
Указатель на `SAFEARRAY` структуры. Конструктор использует этот адрес для создания копии массива, поэтому после создания не используется массив.

### <a name="remarks"></a>Примечания

Создает объект `CComSafeArray`.

##  <a name="dtor"></a>  CComSafeArray:: ~ CComSafeArray

Деструктор

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="copyfrom"></a>  CComSafeArray::CopyFrom

Копирует содержимое объекта `SAFEARRAY` структуры в `CComSafeArray` объекта.

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Параметры

*ppArray*<br/>
Указатель на `SAFEARRAY` для копирования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод копирует содержимое объекта `SAFEARRAY` в текущий `CComSafeArray` объекта. Выполняется замена содержимого существующего массива.

##  <a name="copyto"></a>  CComSafeArray::CopyTo

Создает копию объекта `CComSafeArray`.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Параметры

*ppArray*<br/>
Указатель на расположение, в котором нужно создать объект `SAFEARRAY`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод копирует содержимое объекта `CComSafeArray` в коллекцию `SAFEARRAY` структуры.

##  <a name="create"></a>  CComSafeArray::Create

Создает объект `CComSafeArray`.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>Параметры

*pBound*<br/>
Указатель на объект `SAFEARRAYBOUND` .

*uDims*<br/>
Число измерений в массиве.

*Инициализирует метод ulCount*<br/>
Количество элементов в массиве.

*lLBound*<br/>
Значение нижней границы; то есть индекс первого элемента в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Объект `CComSafeArray` объект может быть создан из существующего `SAFEARRAYBOUND` структуры и число измерений или путем указания числа элементов в массиве и нижняя граница. Если массив должен быть предоставлен доступ из Visual C++, нижней границы должно быть 0. Другие языки могут разрешить другие значения для нижней границы (например, Visual Basic поддерживает массивы с элементами с диапазоном, например 10 до 10).

##  <a name="destroy"></a>  CComSafeArray::Destroy

Уничтожает объект `CComSafeArray`.

```
HRESULT Destroy();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Удаляет существующий `CComSafeArray` объект и все данные, он содержит.

##  <a name="detach"></a>  CComSafeArray::Detach

Отсоединяет `SAFEARRAY` из `CComSafeArray` объекта.

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `SAFEARRAY` объект.

### <a name="remarks"></a>Примечания

Этот метод отсоединяет `SAFEARRAY` объекта из `CComSafeArray` объекта.

##  <a name="getat"></a>  CComSafeArray::GetAt

Получает один элемент из одномерного массива.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Номер индекса в массиве для возврата значения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на элемент массива требуется.

##  <a name="getcount"></a>  CComSafeArray::GetCount

Возвращает число элементов в массиве.

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*uDim*<br/>
Измерение массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает число элементов в массиве.

### <a name="remarks"></a>Примечания

При использовании с многомерным массивом, этот метод вернет число элементов в конкретное измерение.

##  <a name="getdimensions"></a>  CComSafeArray::GetDimensions

Возвращает число измерений в массиве.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число измерений в массиве.

##  <a name="getlowerbound"></a>  CComSafeArray::GetLowerBound

Возвращает нижнюю границу заданного измерения массива.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*uDim*<br/>
Измерение массива, для которого необходимо получить нижняя граница. Если не указано, значение по умолчанию равно 0.

### <a name="return-value"></a>Возвращаемое значение

Возвращает нижнюю границу.

### <a name="remarks"></a>Примечания

Если нижняя граница — 0, это указывает массив, типа C, первый элемент которой является элемент номер 0. В случае ошибки, например, аргумент недопустимый измерения, этот метод вызывает метод `AtlThrow` с HRESULT, описывающее ошибку.

##  <a name="getsafearrayptr"></a>  CComSafeArray::GetSafeArrayPtr

Возвращает адрес элемента данных `m_psa` .

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на [CComSafeArray::m_psa](#m_psa) данные-член.

##  <a name="gettype"></a>  CComSafeArray::GetType

Возвращает тип данных, хранящихся в массиве.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип данных, хранящихся в массиве, который может быть любой из следующих типов:

|VARTYPE|Описание|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|указатель типа decimal|
|VT_VARIANT|указатель типа variant|
|VT_CY|Currency - тип данных|

##  <a name="getupperbound"></a>  CComSafeArray::GetUpperBound

Возвращает верхнюю границу любого измерения массива.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*uDim*<br/>
Измерение массива, для которого необходимо получить верхнюю границу. Если не указано, значение по умолчанию равно 0.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верхнюю границу. Это значение равно включительно, максимальный допустимый индекс для этого измерения.

### <a name="remarks"></a>Примечания

В случае ошибки, например, аргумент недопустимый измерения, этот метод вызывает метод `AtlThrow` с HRESULT, описывающее ошибку.

##  <a name="issizable"></a>  CComSafeArray::IsSizable

Проверяет, можно ли изменить размер объекта `CComSafeArray` .

```
bool IsSizable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если `CComSafeArray` можно изменять, FALSE, если это невозможно.

##  <a name="m_psa"></a>  CComSafeArray::m_psa

Содержит адрес `SAFEARRAY` доступ к структуре.

```
LPSAFEARRAY m_psa;
```

##  <a name="multidimgetat"></a>  CComSafeArray::MultiDimGetAt

Получает один элемент из многомерного массива.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>Параметры

*alIndex*<br/>
Указатель на вектор индексов для каждого измерения в массиве. Крайнего левого (наиболее значительному) является измерение `alIndex[0]`.

*t*<br/>
Ссылка на данные, возвращенные.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="multidimsetat"></a>  CComSafeArray::MultiDimSetAt

Задает значение элемента в многомерном массиве.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>Параметры

*alIndex*<br/>
Указатель на вектор индексов для каждого измерения в массиве. Крайний правый (наименее значительного) измерения является `alIndex`[0].

*T*<br/>
Указывает значение нового элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Это многомерные версия [CComSafeArray::SetAt](#setat).

##  <a name="operator_at"></a>  CComSafeArray::operator \[\]

Получает элемент из массива.

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>Параметры

*Индекс, nIndex*<br/>
Номер индекса обязательный элемент в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент, соответствующий массив.

### <a name="remarks"></a>Примечания

Выполняет ту же функцию [CComSafeArray::GetAt](#getat), однако этот оператор работает только для одномерных массивов.

##  <a name="operator_eq"></a>  CComSafeArray::operator =

Оператор присвоения.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*saSrc*<br/>
Ссылка на объект `CComSafeArray`.

*psaSrc*<br/>
Указатель на объект `SAFEARRAY` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип данных, хранящихся в массиве.

##  <a name="operator_lpsafearray"></a>  CComSafeArray::operator LPSAFEARRAY

Приводит значение к `SAFEARRAY` указатель.

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Возвращаемое значение

Приводит значение к `SAFEARRAY` указатель.

##  <a name="resize"></a>  CComSafeArray::Resize

Изменяет размер объекта `CComSafeArray` .

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>Параметры

*pBound*<br/>
Указатель на `SAFEARRAYBOUND` структуру, содержащую сведения на количество элементов, а нижняя граница массива.

*Инициализирует метод ulCount*<br/>
Запрошенное число объектов в массиве с измененным размером.

*lLBound*<br/>
Нижняя граница.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод изменяет только размер правого измерения. Массивы, которые возвращают размер не будет `IsResizable` со значением FALSE.

##  <a name="setat"></a>  CComSafeArray::SetAt

Задает значение элемента в одномерном массиве.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Индекс элемента в массиве.

*t*<br/>
Новое значение указанного элемента.

*bCopy*<br/>
Указывает, следует ли создавать копию данных. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

*BCopy* флаг учитывается при добавлении элементов типа BSTR и VARIANT в массив. Значение по умолчанию TRUE гарантирует, что новая копия состоит из данных, при добавлении элемента в массиве.

## <a name="see-also"></a>См. также

[SAFEARRAY Data Type](/windows/desktop/api/oaidl/ns-oaidl-tagsafearray)<br/>
[CComSafeArray::Create](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
