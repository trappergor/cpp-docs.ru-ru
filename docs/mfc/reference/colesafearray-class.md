---
title: Класс COleSafeArray | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
dev_langs:
- C++
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a1bad1ccc1671176ce213e59c5d4c8c318a441b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203428"
---
# <a name="colesafearray-class"></a>Класс COleSafeArray
Класс для работы с массивами произвольных типов и измерений.

## <a name="syntax"></a>Синтаксис

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[COleSafeArray::COleSafeArray](#colesafearray)|Создает объект `COleSafeArray`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[COleSafeArray::AccessData](#accessdata)|Извлекает указатель на данные массива.|
|[COleSafeArray::AllocData](#allocdata)|Выделяет память для массива.|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Выделяет память для дескриптора безопасного массива.|
|[COleSafeArray::Attach](#attach)|Контроль существующего `VARIANT` массив `COleSafeArray` объекта.|
|[COleSafeArray::Clear](#clear)|Освобождает все данные в базовом `VARIANT`.|
|[COleSafeArray::Copy](#copy)|Создает копию существующего массива.|
|[COleSafeArray::Create](#create)|Создает безопасный массив.|
|[COleSafeArray::CreateOneDim](#createonedim)|Создает одномерный массив `COleSafeArray` объекта.|
|[COleSafeArray::Destroy](#destroy)|Удаляет существующего массива.|
|[COleSafeArray::DestroyData](#destroydata)|Удаляет данные в безопасном массиве.|
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Уничтожает дескриптор безопасного массива.|
|[COleSafeArray::Detach](#detach)|Отсоединяет массив VARIANT из `COleSafeArray` (таким образом, данные не будут освобождены).|
|[COleSafeArray::GetByteArray](#getbytearray)|Копирует содержимое безопасного массива в [CByteArray](../../mfc/reference/cbytearray-class.md).|
|[COleSafeArray::GetDim](#getdim)|Возвращает число измерений в массиве.|
|[COleSafeArray::GetElement](#getelement)|Получает один элемент безопасного массива.|
|[COleSafeArray::GetElemSize](#getelemsize)|Возвращает размер в байтах, из одного элемента в безопасном массиве.|
|[COleSafeArray::GetLBound](#getlbound)|Возвращает нижнюю границу для любого измерения безопасного массива.|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Возвращает количество элементов одномерного массива `COleSafeArray` объекта.|
|[COleSafeArray::GetUBound](#getubound)|Возвращает верхнюю границу любого измерения безопасного массива.|
|[COleSafeArray::Lock](#lock)|Увеличивает счетчик блокировки массива и помещает указатель на массив данных в его дескриптора.|
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Возвращает указатель на индексированный элемент.|
|[COleSafeArray::PutElement](#putelement)|Помещает в массив один элемент.|
|[COleSafeArray::Redim](#redim)|Изменяет значение младших (крайний справа) границы безопасного массива.|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Изменяет количество элементов в одномерном массиве `COleSafeArray` объекта.|
|[COleSafeArray::UnaccessData](#unaccessdata)|Уменьшает блокировку count массива и делает недействительным указатель, полученных `AccessData`.|
|[COleSafeArray::Unlock](#unlock)|Уменьшает счетчик блокировок в массиве, его может быть освобожден или изменения размера.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Получает доступ к базовой `VARIANT` структуры `COleSafeArray` объекта.|
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Получает доступ к базовой `VARIANT` структуры `COleSafeArray` объекта.|
|[COleSafeArray::operator =](#operator_eq)|Копирует значения в `COleSafeArray` объекта (`SAFEARRAY`, `VARIANT`, `COleVariant`, или `COleSafeArray` массива).|
|[COleSafeArray::operator ==](#operator_eq_eq)|Сравнивает два массива типа variant (`SAFEARRAY`, `VARIANT`, `COleVariant`, или `COleSafeArray` массивов).|
|[COleSafeArray::operator &lt;&lt;](#operator_lt_lt)|Выводит содержимое `COleSafeArray` объекта в контекст дампа.|

## <a name="remarks"></a>Примечания

`COleSafeArray` является производным от OLE `VARIANT` структуры. OLE `SAFEARRAY` функции-члены доступны через `COleSafeArray`, а также как набор функций-членов специально для одномерных массивов байтов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="accessdata"></a>  COleSafeArray::AccessData

Извлекает указатель на данные массива.

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Параметры

*ppvData*<br/>
Указатель на указатель на данные массива.

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

##  <a name="allocdata"></a>  COleSafeArray::AllocData

Выделяет память для безопасного массива.

```
void AllocData();
```

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="allocdescriptor"></a>  COleSafeArray::AllocDescriptor

Выделяет память для дескриптора безопасного массива.

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Параметры

*dwDims*<br/>
Число измерений в безопасном массиве.

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="attach"></a>  COleSafeArray::Attach

Контроль данных в существующем `VARIANT` массив `COleSafeArray` объекта.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
Объект `VARIANT`. *VarSrc* параметр должен иметь VARTYPE [VT_ARRAY](/windows/desktop/api/wtypes/ne-wtypes-varenum).

### <a name="remarks"></a>Примечания

Источник `VARIANT`элемента типа задано значение VT_EMPTY. Эта функция удаляет текущие данные массива, если таковые имеются.

### <a name="example"></a>Пример

  См. в примере [COleSafeArray::AccessData](#accessdata).

##  <a name="clear"></a>  COleSafeArray::Clear

Очищает безопасного массива.

```
void Clear();
```

### <a name="remarks"></a>Примечания

Функция безопасного массива очищается путем установки `VARTYPE` объекта значение VT_EMPTY. Текущее содержимое освобождаются и освобождается массив.

##  <a name="colesafearray"></a>  COleSafeArray::COleSafeArray

Создает объект `COleSafeArray`.

```
COleSafeArray();


COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);


COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
  COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>Параметры

*saSrc*<br/>
Существующий `COleSafeArray` объекта или `SAFEARRAY` необходимо скопировать в новый `COleSafeArray` объекта.

*vtSrc*<br/>
VARTYPE нового `COleSafeArray` объекта.

*psaSrc*<br/>
Указатель на `SAFEARRAY` необходимо скопировать в новый `COleSafeArray` объекта.

*varSrc*<br/>
Существующий `VARIANT` или `COleVariant` объект, который необходимо скопировать в новый `COleSafeArray` объекта.

*pSrc*<br/>
Указатель на `VARIANT` объект, который необходимо скопировать в новый `COleSafeArray` объекта.

### <a name="remarks"></a>Примечания

Все эти конструкторы создают новые `COleSafeArray` объектов. Если параметр не пустой `COleSafeArray` (VT_EMPTY) создается объект. Если `COleSafeArray` копируется из другого массива неявно известна, VARTYPE ( `COleSafeArray`, `COleVariant`, или `VARIANT`), VARTYPE исходного массива сохраняется и не нужно указывать. Если `COleSafeArray` копируется из другого массива неизвестен, VARTYPE (`SAFEARRAY`), VARTYPE должно быть указано в *vtSrc* параметра.

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="copy"></a>  COleSafeArray::Copy

Создает копию существующего безопасного массива.

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Параметры

*ppsa*<br/>
Указатель на расположение, в которую будет возвращен новый дескриптор массива.

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="create"></a>  COleSafeArray::Create

Выделяет и инициализирует данные для массива.

```
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);


void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>Параметры

*vtSrc*<br/>
Базовый тип массива (то есть VARTYPE каждого элемента массива). VARTYPE поддерживается только для подмножества типов variant. Можно задать ни VT_ARRAY, ни флагом VT_BYREF. Значение VT_EMPTY и VT_NULL не являются допустимым базовые типы для массива. Все остальные типы являются допустимыми.

*dwDims*<br/>
Число измерений в массиве. Это можно изменить после создания массива с [Redim](#redim).

*rgElements*<br/>
Указатель на массив из количества элементов для каждого измерения в массиве.

*rgsabounds*<br/>
Указатель на вектор (по одному для каждого измерения) границы для выделения для массива.

### <a name="remarks"></a>Примечания

Эта функция будет очистить текущие данные массива, при необходимости. В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="createonedim"></a>  COleSafeArray::CreateOneDim

Создает новый одномерный `COleSafeArray` объекта.

```
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Параметры

*vtSrc*<br/>
Базовый тип массива (то есть VARTYPE каждого элемента массива).

*dwElements*<br/>
Число элементов в массиве. Это можно изменить после создания массива с [ResizeOneDim](#resizeonedim).

*pvSrcData*<br/>
Указатель на данные для копирования в массив.

*nLBound*<br/>
Нижняя граница массива.

### <a name="remarks"></a>Примечания

Функция выделяет и инициализирует данные для массива, копирование указанных данных в том случае, если указатель *pvSrcData* не равно NULL.

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

##  <a name="destroy"></a>  COleSafeArray::Destroy

Уничтожает дескриптор существующего массива и все данные в массиве.

```
void Destroy();
```

### <a name="remarks"></a>Примечания

Если объекты хранятся в массиве, каждый объект освобождается. В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="destroydata"></a>  COleSafeArray::DestroyData

Уничтожает все данные в безопасном массиве.

```
void DestroyData();
```

### <a name="remarks"></a>Примечания

Если объекты хранятся в массиве, каждый объект освобождается. В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="destroydescriptor"></a>  COleSafeArray::DestroyDescriptor

Уничтожает дескриптор безопасного массива.

```
void DestroyDescriptor();
```

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="detach"></a>  COleSafeArray::Detach

Отсоединяет `VARIANT` данные из `COleSafeArray` объекта.

```
VARIANT Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Базовый `VARIANT` значение в `COleSafeArray` объекта.

### <a name="remarks"></a>Примечания

Функция отсоединяет данные в безопасном массиве, задав VARTYPE объекта значение VT_EMPTY. Это обязанность вызывающего освобождение массива путем вызова функции Windows [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear).

В случае ошибки функция выдает [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

  См. в примере [COleSafeArray::PutElement](#putelement).

##  <a name="getbytearray"></a>  COleSafeArray::GetByteArray

Копирует содержимое безопасного массива в `CByteArray`.

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Параметры

*байт*<br/>
Ссылку на [CByteArray](../../mfc/reference/cbytearray-class.md) объекта.

##  <a name="getdim"></a>  COleSafeArray::GetDim

Возвращает число измерений в `COleSafeArray` объекта.

```
DWORD GetDim();
```

### <a name="return-value"></a>Возвращаемое значение

Число измерений в безопасном массиве.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="getelement"></a>  COleSafeArray::GetElement

Получает один элемент безопасного массива.

```
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Параметры

*rgIndices*<br/>
Указатель на массив индексов для каждого измерения массива.

*pvData*<br/>
Указатель на место для размещения элемента массива.

### <a name="remarks"></a>Примечания

Эта функция автоматически вызывает функций windows `SafeArrayLock` и `SafeArrayUnlock` до и после получения элемента. Если элемент данных является строка, объект или вариант, функция копирует элемент в правильный способ использования. Параметр *pvData* должен указывать на большой достаточный буфер, содержащий элемент.

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

##  <a name="getelemsize"></a>  COleSafeArray::GetElemSize

Получает размер элемента в `COleSafeArray` объекта.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Возвращаемое значение

Размер в байтах, элементов безопасного массива.

##  <a name="getlbound"></a>  COleSafeArray::GetLBound

Возвращает нижнюю границу для любого измерения массива `COleSafeArray` объекта.

```
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Параметры

*dwDim*<br/>
Измерение массива, для которого необходимо получить нижняя граница.

*pLBound*<br/>
Указатель на местоположение для возврата нижняя граница.

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

##  <a name="getonedimsize"></a>  COleSafeArray::GetOneDimSize

Возвращает количество элементов одномерного массива `COleSafeArray` объекта.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в одномерном массиве safe.

### <a name="example"></a>Пример

  См. в примере [COleSafeArray::CreateOneDim](#createonedim).

##  <a name="getubound"></a>  COleSafeArray::GetUBound

Возвращает верхнюю границу любого измерения безопасного массива.

```
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Параметры

*dwDim*<br/>
Измерение массива, для которого необходимо получить верхнюю границу.

*pUBound*<br/>
Указатель на местоположение для возврата верхней границы.

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

##  <a name="lock"></a>  COleSafeArray::Lock

Увеличивает счетчик блокировки массивом и поместить указатель на массив данных в его дескриптора.

```
void Lock();
```

### <a name="remarks"></a>Примечания

В случае ошибки создает [COleException](../../mfc/reference/coleexception-class.md).

Указатель на дескриптор массива действителен `Unlock` вызывается. Вызовы `Lock` могут быть вложенными; одинаковое число вызовов `Unlock` являются обязательными.

Массив нельзя удалить, пока он заблокирован.

##  <a name="operator_lpcvariant"></a>  COleSafeArray::operator LPCVARIANT

Вызовите этот оператор приведения, чтобы получить доступ к базовой `VARIANT` структуры для этого `COleSafeArray` объекта.

```
operator LPCVARIANT() const;
```

##  <a name="operator_lpvariant"></a>  COleSafeArray::operator LPVARIANT

Вызовите этот оператор приведения, чтобы получить доступ к базовой `VARIANT` структуры для этого `COleSafeArray` объекта.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Примечания

Обратите внимание, что изменение значения в `VARIANT` структуры осуществляется указатель, возвращаемый этой функцией изменится значение этой `COleSafeArray` объекта.

##  <a name="operator_eq"></a>  COleSafeArray::operator =

Эти перегруженных операторах присваивания копирования исходного значения в данный `COleSafeArray` объекта.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
  COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Примечания

Краткое описание каждого оператора выглядит следующим образом:

- **оператор = (** *saSrc* **)** копирует существующий `COleSafeArray` объект в этот объект.

- **оператор = (** *varSrc* **)** копирует существующий `VARIANT` или `COleVariant` массив, в этот объект.

- **оператор = (** *pSrc* **)** копий `VARIANT` объект массива, к которому *pSrc* в этот объект.

##  <a name="operator_eq_eq"></a>  COleSafeArray::operator ==

Этот оператор сравнивает два массива (`SAFEARRAY`, `VARIANT`, `COleVariant`, или `COleSafeArray` массивы) и возвращает ненулевое значение, если они равны; в противном случае — 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Примечания

Два массива равны, если они имеют одинаковое число измерений, одинаковый размер каждого измерения, а значения равны элементов.

##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;

`COleSafeArray` Вставки (<<) поддерживает оператор диагностики создания дампа и хранению `COleSafeArray` объекта в архив.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex

Возвращает указатель на элемент, указанный значениями индекса.

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Параметры

*rgIndices*<br/>
Массив значений индекса, идентифицирующих элемент массива. Необходимо указать все индексы для элемента.

*ppvData*<br/>
По возвращении указатель для элемента, определяемого по значениям в *rgIndices*.

##  <a name="putelement"></a>  COleSafeArray::PutElement

Помещает в массив один элемент.

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Параметры

*rgIndices*<br/>
Указатель на массив индексов для каждого измерения массива.

*pvData*<br/>
Указатель на данные, которые требуется поместить в массив. Типы variant VT_DISPATCH VT_UNKNOWN и VT_BSTR являются указателями и не требуют других уровней косвенных обращений.

### <a name="remarks"></a>Примечания

Эта функция автоматически вызывает функции Windows [SafeArrayLock](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraylock) и [SafeArrayUnlock](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearrayunlock) до и после назначения элемента. Если строка, объект или вариант являются элементом данных, функция выполняет правильное копирование, а если существующим элементом — правильное удаление.

Обратите внимание, для массива можно настроить несколько блокировок, поэтому вы можете поместить в него элементы, недоступные для других операций.

В случае ошибки функция выдает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

##  <a name="redim"></a>  COleSafeArray::Redim

Изменяет значение младших (крайний справа) границы безопасного массива.

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Параметры

*psaboundNew*<br/>
Указатель на новый безопасный массив привязать структуру, содержащую новые границы массива. Может быть изменен только наименее значительного измерения массива.

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim

Изменяет количество элементов в одномерном массиве `COleSafeArray` объекта.

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Параметры

*dwElements*<br/>
Число элементов в одномерном массиве safe.

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

  См. в примере [COleSafeArray::CreateOneDim](#createonedim).

##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData

Уменьшает блокировку count массива и делает недействительным указатель, полученных `AccessData`.

```
void UnaccessData();
```

### <a name="remarks"></a>Примечания

В случае ошибки функция выдает [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

  См. в примере [COleSafeArray::AccessData](#accessdata).

##  <a name="unlock"></a>  COleSafeArray::Unlock

Уменьшает счетчик блокировок в массиве, его может быть освобожден или изменения размера.

```
void Unlock();
```

### <a name="remarks"></a>Примечания

Эта функция вызывается по завершении доступ к данным в массиве. В случае ошибки создает [COleException](../../mfc/reference/coleexception-class.md).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleVariant](../../mfc/reference/colevariant-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
