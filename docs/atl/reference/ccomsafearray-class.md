---
title: Класс CComSafeArray
ms.date: 05/06/2019
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
ms.openlocfilehash: 79b1dc844f53f739dc48eb6177e57810ff0c8412
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739593"
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

|name|Описание|
|----------|-----------------|
|[CComSafeArray:: CComSafeArray](#ccomsafearray)|Конструктор.|
|[CComSafeArray:: ~ CComSafeArray](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComSafeArray:: Add](#add)|Добавляет один или несколько элементов или `SAFEARRAY` структуру `CComSafeArray`в.|
|[CComSafeArray::Attach](#attach)|Присоединяет `CComSafeArray` структуру к объекту. `SAFEARRAY`|
|[CComSafeArray:: CopyFrom](#copyfrom)|Копирует содержимое `SAFEARRAY` структуры `CComSafeArray` в объект.|
|[CComSafeArray:: CopyTo](#copyto)|Создает копию объекта `CComSafeArray`.|
|[CComSafeArray::Create](#create)|Создает объект `CComSafeArray`.|
|[CComSafeArray::Destroy](#destroy)|Уничтожает объект `CComSafeArray`.|
|[CComSafeArray::D етач](#detach)|Отсоединяет `CComSafeArray` объект отобъекта.`SAFEARRAY`|
|[CComSafeArray:: GetAt](#getat)|Получает один элемент из одномерного массива.|
|[CComSafeArray:: NOCOUNT](#getcount)|Возвращает число элементов в массиве.|
|[CComSafeArray:: Dimension](#getdimensions)|Возвращает число измерений в массиве.|
|[CComSafeArray:: Жетловербаунд](#getlowerbound)|Возвращает нижнюю границу заданного измерения массива.|
|[CComSafeArray:: Жетсафеаррайптр](#getsafearrayptr)|Возвращает адрес элемента данных `m_psa` .|
|[CComSafeArray:: GetType](#gettype)|Возвращает тип данных, хранящихся в массиве.|
|[CComSafeArray:: GetUpperBound](#getupperbound)|Возвращает верхнюю границу любого измерения массива.|
|[CComSafeArray:: имеет размер](#issizable)|Проверяет, можно ли изменить размер объекта `CComSafeArray` .|
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|Получает один элемент из многомерного массива.|
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|Задает значение элемента в многомерном массиве.|
|[CComSafeArray:: изменение размера](#resize)|Изменяет размер объекта `CComSafeArray` .|
|[CComSafeArray:: SetAt](#setat)|Задает значение элемента в одномерном массиве.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CComSafeArray:: operator ЛПСАФЕАРРАЙ](#operator_lpsafearray)|Приводит значение к `SAFEARRAY` указателю.|
|[CComSafeArray:: operator\[\]](ccomsafearray-class.md#operator_at)|Получает элемент из массива.|
|[CComSafeArray:: operator =](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CComSafeArray:: m_psa](#m_psa)|Этот элемент данных содержит адрес `SAFEARRAY` структуры.|

## <a name="remarks"></a>Примечания

`CComSafeArray` предоставляет оболочку для класса [SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray) , упрощая создание одно- и многомерных массивов практически любого поддерживаемого типа VARIANT и управление ими.

`CComSafeArray` упрощает передачу массивов между процессами и обеспечивает дополнительную безопасность путем проверки значений индекса массива на соответствие верхней и нижней границам.

Нижняя граница `CComSafeArray` может начинаться с любого определенного пользователем значения. Однако нижняя граница массивов, доступ к которым осуществляется через C++, должна быть равна 0. В других языках, например Visual Basic, могут использоваться другие ограничивающие значения (например, от −10 до 10).

Используйте [CComSafeArray::Create](#create) для создания объекта `CComSafeArray` , и [CComSafeArray::Destroy](#destroy) — для его удаления.

`CComSafeArray` может содержать следующее подмножество типов данных VARIANT.

|VARTYPE|Описание|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|ssNoversion|
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

##  <a name="add"></a>CComSafeArray:: Add

Добавляет один или несколько элементов или `SAFEARRAY` структуру `CComSafeArray`в.

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Параметры

*псасрк*<br/>
Указатель на объект `SAFEARRAY` .

*улкаунт*<br/>
Число объектов, добавляемых в массив.

*Лутор*<br/>
Указатель на один или несколько объектов, добавляемых в массив.

*t*<br/>
Ссылка на объект, добавляемый в массив.

*бкопи*<br/>
Указывает, следует ли создавать копию данных. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Новые объекты добавляются в конец существующего `SAFEARRAY` объекта. Добавление объекта в многомерный `SAFEARRAY` объект не поддерживается. При добавлении существующего массива объектов оба массива должны содержать элементы одного типа.

Флаг *бкопи* учитывается при добавлении элементов типа BSTR или Variant в массив. Значение по умолчанию TRUE гарантирует, что при добавлении элемента в массив будет создана новая копия данных.

##  <a name="attach"></a>CComSafeArray:: Attach

Присоединяет `CComSafeArray` структуру к объекту. `SAFEARRAY`

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*псасрк*<br/>
Указатель на `SAFEARRAY` структуру.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Присоединяет `CComSafeArray` `CComSafeArray` структуру к объекту, делая доступными существующие методы. `SAFEARRAY`

##  <a name="ccomsafearray"></a>CComSafeArray:: CComSafeArray

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

*выход*<br/>
Структура `SAFEARRAYBOUND`.

*улкаунт*<br/>
Количество элементов в массиве.

*ллбаунд*<br/>
Значение нижней границы; то есть индекс первого элемента в массиве.

*пбаунд*<br/>
Указатель на `SAFEARRAYBOUND` структуру.

*удимс*<br/>
Число измерений в массиве.

*сасрк*<br/>
Ссылка на `SAFEARRAY` структуру или `CComSafeArray` объект. В любом случае конструктор использует эту ссылку для создания копии массива, поэтому на массив не ссылаются после создания.

*псасрк*<br/>
Указатель на `SAFEARRAY` структуру. Конструктор использует этот адрес для создания копии массива, поэтому на массив не ссылаются после создания.

### <a name="remarks"></a>Примечания

Создает объект `CComSafeArray`.

##  <a name="dtor"></a>CComSafeArray:: ~ CComSafeArray

Деструктор

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="copyfrom"></a>CComSafeArray:: CopyFrom

Копирует содержимое `SAFEARRAY` структуры `CComSafeArray` в объект.

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Параметры

*ппаррай*<br/>
Указатель на копируемый объект `SAFEARRAY` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Этот метод копирует содержимое `SAFEARRAY` объекта в текущий `CComSafeArray` объект. Существующее содержимое массива заменяется.

##  <a name="copyto"></a>CComSafeArray:: CopyTo

Создает копию объекта `CComSafeArray`.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Параметры

*ппаррай*<br/>
Указатель на расположение, в котором создается новый `SAFEARRAY`объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Этот метод копирует содержимое `CComSafeArray` объекта `SAFEARRAY` в структуру.

##  <a name="create"></a>  CComSafeArray::Create

Создает объект `CComSafeArray`.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>Параметры

*пбаунд*<br/>
Указатель на объект `SAFEARRAYBOUND` .

*удимс*<br/>
Число измерений в массиве.

*улкаунт*<br/>
Количество элементов в массиве.

*ллбаунд*<br/>
Значение нижней границы; то есть индекс первого элемента в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Объект может быть создан из существующей `SAFEARRAYBOUND` структуры и числа измерений или путем указания количества элементов в массиве и нижней границы. `CComSafeArray` Если доступ к массиву осуществляется из C++, Нижняя граница должна быть равна 0. Другие языки могут допускать другие значения для нижней границы (например, Visual Basic поддерживает массивы с элементами с диапазоном, например от-10 до 10).

##  <a name="destroy"></a>  CComSafeArray::Destroy

Уничтожает объект `CComSafeArray`.

```
HRESULT Destroy();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Уничтожает существующий `CComSafeArray` объект и все содержащиеся в нем данные.

##  <a name="detach"></a>CComSafeArray::D етач

Отсоединяет `CComSafeArray` объект отобъекта.`SAFEARRAY`

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `SAFEARRAY` объект.

### <a name="remarks"></a>Примечания

Этот метод отсоединяет `SAFEARRAY` объект `CComSafeArray` от объекта.

##  <a name="getat"></a>CComSafeArray:: GetAt

Получает один элемент из одномерного массива.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>Параметры

*линдекс*<br/>
Номер индекса возвращаемого значения в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на требуемый элемент массива.

##  <a name="getcount"></a>CComSafeArray:: NOCOUNT

Возвращает число элементов в массиве.

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*удим*<br/>
Измерение массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает число элементов в массиве.

### <a name="remarks"></a>Примечания

При использовании с многомерным массивом этот метод возвратит количество элементов только в определенном измерении.

##  <a name="getdimensions"></a>CComSafeArray:: Dimension

Возвращает число измерений в массиве.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число измерений в массиве.

##  <a name="getlowerbound"></a>CComSafeArray:: Жетловербаунд

Возвращает нижнюю границу заданного измерения массива.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*удим*<br/>
Измерение массива, для которого необходимо получить нижнюю границу. Если этот параметр опущен, по умолчанию используется значение 0.

### <a name="return-value"></a>Возвращаемое значение

Возвращает нижнюю границу.

### <a name="remarks"></a>Примечания

Если нижняя граница равна 0, это указывает на C-Like массив, первый элемент которого имеет номер элемента 0. В случае ошибки, например недопустимого аргумента измерения, этот метод вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

##  <a name="getsafearrayptr"></a>CComSafeArray:: Жетсафеаррайптр

Возвращает адрес элемента данных `m_psa` .

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на элемент данных [CComSafeArray:: m_psa](#m_psa) .

##  <a name="gettype"></a>CComSafeArray:: GetType

Возвращает тип данных, хранящихся в массиве.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип данных, хранящихся в массиве, который может иметь любой из следующих типов:

|VARTYPE|Описание|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|ssNoversion|
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

##  <a name="getupperbound"></a>CComSafeArray:: GetUpperBound

Возвращает верхнюю границу любого измерения массива.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*удим*<br/>
Измерение массива, для которого необходимо получить верхнюю границу. Если этот параметр опущен, по умолчанию используется значение 0.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верхнюю границу. Это значение является инклюзивным, максимально допустимым индексом для этого измерения.

### <a name="remarks"></a>Примечания

В случае ошибки, например недопустимого аргумента измерения, этот метод вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

##  <a name="issizable"></a>CComSafeArray:: имеет размер

Проверяет, можно ли изменить размер объекта `CComSafeArray` .

```
bool IsSizable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, `CComSafeArray` если можно изменить размер, и false в противном случае.

##  <a name="m_psa"></a>CComSafeArray:: m_psa

Содержит адрес структуры, `SAFEARRAY` к которой осуществлялся доступ.

```
LPSAFEARRAY m_psa;
```

##  <a name="multidimgetat"></a>  CComSafeArray::MultiDimGetAt

Получает один элемент из многомерного массива.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>Параметры

*алиндекс*<br/>
Указатель на вектор индексов для каждого измерения в массиве. Самое левое (наиболее значимое) измерение `alIndex[0]`—.

*t*<br/>
Ссылка на возвращаемые данные.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

##  <a name="multidimsetat"></a>  CComSafeArray::MultiDimSetAt

Задает значение элемента в многомерном массиве.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>Параметры

*алиндекс*<br/>
Указатель на вектор индексов для каждого измерения в массиве. Самое правое (самое важное) измерение `alIndex`— [0].

*T*<br/>
Задает значение нового элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Это многомерная версия [CComSafeArray:: SetAt](#setat).

##  <a name="operator_at"></a>CComSafeArray:: operator\[\]

Получает элемент из массива.

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>Параметры

*Линдекс, Ниндекс*<br/>
Номер индекса требуемого элемента в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает соответствующий элемент массива.

### <a name="remarks"></a>Примечания

Выполняет аналогичную функцию для [CComSafeArray:: GetAt](#getat), однако этот оператор работает только с одномерным массивами.

##  <a name="operator_eq"></a>CComSafeArray:: operator =

Оператор присвоения.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*сасрк*<br/>
Ссылка на объект `CComSafeArray`.

*псасрк*<br/>
Указатель на объект `SAFEARRAY` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип данных, хранящихся в массиве.

##  <a name="operator_lpsafearray"></a>CComSafeArray:: operator ЛПСАФЕАРРАЙ

Приводит значение к `SAFEARRAY` указателю.

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Возвращаемое значение

Приводит значение к `SAFEARRAY` указателю.

##  <a name="resize"></a>CComSafeArray:: изменение размера

Изменяет размер объекта `CComSafeArray` .

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>Параметры

*пбаунд*<br/>
Указатель на `SAFEARRAYBOUND` структуру, содержащую сведения о количестве элементов и нижней границе массива.

*улкаунт*<br/>
Запрошенное число объектов в массиве с измененным размером.

*ллбаунд*<br/>
Нижняя граница.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Этот метод изменяет размер только крайнего правого измерения. Он не будет изменять размер массивов, `IsResizable` которые возвращают значение false.

##  <a name="setat"></a>CComSafeArray:: SetAt

Задает значение элемента в одномерном массиве.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Параметры

*линдекс*<br/>
Номер индекса элемента массива, который необходимо задать.

*t*<br/>
Новое значение указанного элемента.

*бкопи*<br/>
Указывает, следует ли создавать копию данных. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Флаг *бкопи* учитывается при добавлении элементов типа BSTR или Variant в массив. Значение по умолчанию TRUE гарантирует, что при добавлении элемента в массив будет создана новая копия данных.

## <a name="see-also"></a>См. также

[Тип данных SAFEARRAY](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[CComSafeArray::Create](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
