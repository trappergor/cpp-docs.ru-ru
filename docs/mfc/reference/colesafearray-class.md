---
title: "Класс COleSafeArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- COleSafeArray class
- arrays [C++], safe
- safe arrays
- ODBC, safe arrays
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3cb6fa49e3adf7e14c34baf7feb64d12e54f2758
ms.lasthandoff: 02/24/2017

---
# <a name="colesafearray-class"></a>Класс COleSafeArray
Класс для работы с массивами произвольных типов и измерений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](#colesafearray)|Создает объект `COleSafeArray`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleSafeArray::AccessData](#accessdata)|Извлекает указатель на массив данных.|  
|[COleSafeArray::AllocData](#allocdata)|Выделяет память для массива.|  
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Выделяет память для дескриптора безопасного массива.|  
|[COleSafeArray::Attach](#attach)|Контроль существующего **VARIANT** массива `COleSafeArray` объекта.|  
|[COleSafeArray::Clear](#clear)|Освобождает все данные в базовом **VARIANT**.|  
|[COleSafeArray::Copy](#copy)|Создает копию существующего массива.|  
|[COleSafeArray::Create](#create)|Создает безопасный массив.|  
|[COleSafeArray::CreateOneDim](#createonedim)|Создает одномерный массив `COleSafeArray` объекта.|  
|[COleSafeArray::Destroy](#destroy)|Удаляет существующий массив.|  
|[COleSafeArray::DestroyData](#destroydata)|Удаляет данные в безопасном массиве.|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Уничтожает дескриптор безопасного массива.|  
|[COleSafeArray::Detach](#detach)|Отсоединяет **VARIANT** массива из `COleSafeArray` (таким образом, чтобы данные не будут освобождены).|  
|[COleSafeArray::GetByteArray](#getbytearray)|Копирует содержимое безопасного массива в [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](#getdim)|Возвращает число измерений в массиве.|  
|[COleSafeArray::GetElement](#getelement)|Возвращает единственный элемент безопасного массива.|  
|[COleSafeArray::GetElemSize](#getelemsize)|Возвращает размер в байтах, из одного элемента в безопасном массиве.|  
|[COleSafeArray::GetLBound](#getlbound)|Возвращает нижнюю границу для любого измерения безопасного массива.|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Возвращает количество элементов в одномерном массиве `COleSafeArray` объекта.|  
|[COleSafeArray::GetUBound](#getubound)|Возвращает верхнюю границу для любого измерения безопасного массива.|  
|[COleSafeArray::Lock](#lock)|Увеличивает значение счетчика блокировки массив и помещает указатель на данные массива в массив дескрипторов.|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Возвращает указатель индексированного элемента.|  
|[COleSafeArray::PutElement](#putelement)|Помещает в массив один элемент.|  
|[COleSafeArray::Redim](#redim)|Изменяет значение младших (крайний справа) границы безопасного массива.|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Изменяет количество элементов в одномерном массиве `COleSafeArray` объекта.|  
|[COleSafeArray::UnaccessData](#unaccessdata)|Уменьшает блокировку подсчета массива и делает недействительным указателя, полученное с `AccessData`.|  
|[COleSafeArray::Unlock](#unlock)|Уменьшает на единицу счетчик блокировок массива, чтобы освободить или изменении размера.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Обращается к основной **VARIANT** структуры `COleSafeArray` объекта.|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Обращается к основной **VARIANT** структуры `COleSafeArray` объекта.|  
|[COleSafeArray::operator =](#operator_eq)|Копирует значения в `COleSafeArray` объекта ( **SAFEARRAY**, **VARIANT**, `COleVariant`, или `COleSafeArray` массива).|  
|[COleSafeArray::operator ==](#operator_eq_eq)|Сравнивает два массива типа variant ( **SAFEARRAY**, **ВАРИАНТ**, `COleVariant`, или `COleSafeArray` массивы).|  
|[COleSafeArray::operator&lt;&lt;](#operator_lt_lt)|Выводит содержимое `COleSafeArray` объекта в контекст дампа.|  
  
## <a name="remarks"></a>Примечания  
 `COleSafeArray`является производным от OLE **VARIANT** структуры. OLE **SAFEARRAY** функции-члены доступны через `COleSafeArray`, а также как набор функций-членов специально для одномерных массивов байтов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="accessdata"></a>COleSafeArray::AccessData  
 Извлекает указатель на массив данных.  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>Параметры  
 `ppvData`  
 Указатель на указатель на массив данных.  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#26;](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="allocdata"></a>COleSafeArray::AllocData  
 Выделяет память для безопасного массива.  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor  
 Выделяет память для дескриптора безопасного массива.  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDims`  
 Число измерений в безопасном массиве.  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="attach"></a>COleSafeArray::Attach  
 Контроль данных в существующий **VARIANT** массива `COleSafeArray` объекта.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *varSrc*  
 Объект **VARIANT** объекта. *VarSrc* параметр должен иметь [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**то есть VT_ARRAY**.  
  
### <a name="remarks"></a>Примечания  
 Источник **VARIANT**в тип имеет значение `VT_EMPTY`. Эта функция очищает текущий массивы данных, при их наличии.  
  
### <a name="example"></a>Пример  
  В примере показано [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="clear"></a>COleSafeArray::Clear  
 Очищает безопасного массива.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Функция очищает безопасного массива, задав `VARTYPE` объекта `VT_EMPTY`. Текущее содержимое освобождаются и освобождается массив.  
  
##  <a name="colesafearray"></a>COleSafeArray::COleSafeArray  
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
 `saSrc`  
 Существующий `COleSafeArray` объекта или **SAFEARRAY** необходимо скопировать в новый `COleSafeArray` объекта.  
  
 `vtSrc`  
 **VARTYPE** нового `COleSafeArray` объекта.  
  
 `psaSrc`  
 Указатель на **SAFEARRAY** необходимо скопировать в новый `COleSafeArray` объекта.  
  
 *varSrc*  
 Существующий **VARIANT** или `COleVariant` скопировать в новый объект `COleSafeArray` объект.  
  
 `pSrc`  
 Указатель на **VARIANT** скопировать в новый объект `COleSafeArray` объект.  
  
### <a name="remarks"></a>Примечания  
 Все эти конструкторы создать `COleSafeArray` объектов. Если параметр не пустой `COleSafeArray` создается объект ( `VT_EMPTY`). Если `COleSafeArray` копируется из другого массива, [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) известен неявно ( `COleSafeArray`, `COleVariant`, или **VARIANT**), **VARTYPE** источника массива сохраняется и не обязательно. Если `COleSafeArray` копируется из другого массива, **VARTYPE** неизвестен ( **SAFEARRAY**), **VARTYPE** должен быть указан в `vtSrc` параметр.  
  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="copy"></a>COleSafeArray::Copy  
 Создает копию существующего безопасного массива.  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>Параметры  
 *ppsa*  
 Указатель на расположение, в котором требуется вернуть новый дескриптор массива.  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="create"></a>COleSafeArray::Create  
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
 `vtSrc`  
 Базовый тип массива (то есть, **VARTYPE** каждого элемента массива). **VARTYPE** предназначен только для подмножества типов variant. Ни **то есть VT_ARRAY** ни **VT_BYREF** можно установить флаг. `VT_EMPTY`и **VT_NULL** не являются допустимым базовые типы для массива. Все другие типы являются допустимыми.  
  
 `dwDims`  
 Число измерений в массиве. Это можно изменить после создания массива с [Redim](#redim).  
  
 *rgElements*  
 Указатель на массив количество элементов для каждого измерения в массиве.  
  
 *rgsabounds*  
 Указатель на объект vector границы (по одному для каждого измерения) для выделения для массива.  
  
### <a name="remarks"></a>Примечания  
 Эта функция очистит текущего массива данных, при необходимости. При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="createonedim"></a>COleSafeArray::CreateOneDim  
 Создает новый одномерный `COleSafeArray` объекта.  
  
```  
void CreateOneDim(
    VARTYPE vtSrc,  
    DWORD dwElements,  
    const void* pvSrcData = NULL,  
    long nLBound = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `vtSrc`  
 Базовый тип массива (то есть, **VARTYPE** каждого элемента массива).  
  
 `dwElements`  
 Число элементов в массиве. Это можно изменить после создания массива с [ResizeOneDim](#resizeonedim).  
  
 `pvSrcData`  
 Указатель на данные, копируемых в массив.  
  
 *nLBound*  
 Нижняя граница массива.  
  
### <a name="remarks"></a>Примечания  
 Функция выделяет и инициализирует данных для массива, копирует указанные данные, если указатель `pvSrcData` не **NULL**.  
  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#28;](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="destroy"></a>COleSafeArray::Destroy  
 Уничтожает дескриптор существующего массива и все данные в массиве.  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>Примечания  
 Если объекты хранятся в массиве, каждый объект освобождается. При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydata"></a>COleSafeArray::DestroyData  
 Удаляет все данные безопасного массива.  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>Примечания  
 Если объекты хранятся в массиве, каждый объект освобождается. При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor  
 Уничтожает дескриптор безопасного массива.  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="detach"></a>COleSafeArray::Detach  
 Отсоединяет **VARIANT** данные `COleSafeArray` объекта.  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовый **VARIANT** значение в `COleSafeArray` объекта.  
  
### <a name="remarks"></a>Примечания  
 Функция отсоединяет данные в безопасном массиве, задав [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) объекта `VT_EMPTY`. Это вызывающим освободить массив путем вызова функции Windows [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835).  
  
 При возникновении ошибки функция создает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
  В примере показано [COleSafeArray::PutElement](#putelement).  
  
##  <a name="getbytearray"></a>COleSafeArray::GetByteArray  
 Копирует содержимое безопасного массива в `CByteArray`.  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Параметры  
 `bytes`  
 Ссылку на [CByteArray](../../mfc/reference/cbytearray-class.md) объекта.  
  
##  <a name="getdim"></a>COleSafeArray::GetDim  
 Возвращает количество измерений в `COleSafeArray` объекта.  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число измерений в безопасном массиве.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="getelement"></a>COleSafeArray::GetElement  
 Возвращает единственный элемент безопасного массива.  
  
```  
void GetElement(
    long* rgIndices,  
    void* pvData);
```  
  
### <a name="parameters"></a>Параметры  
 `rgIndices`  
 Указатель на массив индексов для каждого измерения массива.  
  
 `pvData`  
 Указатель на расположение элемента массива.  
  
### <a name="remarks"></a>Примечания  
 Эта функция автоматически вызывает функции windows `SafeArrayLock` и `SafeArrayUnlock` до и после получения элемента. Если элемент данных является строка, объект или вариант, функция копирует элемент в правильный способ. Параметр `pvData` должен указывать большой достаточно большого буфера содержит элемент.  
  
 При возникновении ошибки функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#29;](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="getelemsize"></a>COleSafeArray::GetElemSize  
 Получает размер элемента в `COleSafeArray` объекта.  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в байтах, безопасный массив элементов.  
  
##  <a name="getlbound"></a>COleSafeArray::GetLBound  
 Возвращает нижнюю границу размерности `COleSafeArray` объекта.  
  
```  
void GetLBound(
    DWORD dwDim,  
    long* pLBound);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDim`  
 Измерение массива, для которого нужно получить нижняя граница.  
  
 *pLBound*  
 Указатель на расположение, чтобы вернуть нижнюю границу.  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки функция создает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#30;](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="getonedimsize"></a>COleSafeArray::GetOneDimSize  
 Возвращает количество элементов в одномерном массиве `COleSafeArray` объекта.  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в одномерном массиве safe.  
  
### <a name="example"></a>Пример  
  В примере показано [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="getubound"></a>COleSafeArray::GetUBound  
 Возвращает верхнюю границу для любого измерения безопасного массива.  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDim`  
 Измерение массива, для которого необходимо получить значение верхней границы.  
  
 *pUBound*  
 Указатель на расположение для возврата верхней границы.  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки функция создает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#31;](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="lock"></a>COleSafeArray::Lock  
 Увеличивает число блокировок массиве и поместите указатель в массив дескрипторов данных массива.  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>Примечания  
 При возникновении ошибки, он вызывает [COleException](../../mfc/reference/coleexception-class.md).  
  
 Указатель на массив дескрипторов действителен `Unlock` вызывается. Вызовы `Lock` могут быть вложенными; равно числу вызовов `Unlock` являются обязательными.  
  
 Массив нельзя удалить, пока он заблокирован.  
  
##  <a name="operator_lpcvariant"></a>COleSafeArray::operator LPCVARIANT  
 Вызовите этот оператор приведения для доступа к основной **VARIANT** структуры для этого `COleSafeArray` объекта.  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="operator_lpvariant"></a>COleSafeArray::operator LPVARIANT  
 Вызовите этот оператор приведения для доступа к основной **VARIANT** структуры для этого `COleSafeArray` объекта.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что изменение значения в **VARIANT** структуры осуществляется указатель, возвращаемый этой функцией приведет к изменению значения этого `COleSafeArray` объекта.  
  
##  <a name="operator_eq"></a>COleSafeArray::operator =  
 Эти перегруженных операторах присваивания скопируйте исходное значение в это `COleSafeArray` объекта.  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Примечания  
 Краткое описание каждого оператора выглядит следующим образом:  
  
- **оператор = (** *saSrc* **)** копирует существующую `COleSafeArray` в этот объект.  
  
- **оператор = (** *varSrc***)** копирует существующую **VARIANT** или `COleVariant` массив в этот объект.  
  
- **оператор = (** `pSrc` **)** копии **VARIANT** объект массива осуществляется `pSrc` в этот объект.  
  
##  <a name="operator_eq_eq"></a>COleSafeArray::operator ==  
 Этот оператор сравнивает два массива ( **SAFEARRAY**, **VARIANT**, `COleVariant`, или `COleSafeArray` массивы) и возвращает ненулевое значение, если они равны; в противном случае — 0.  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
Оператор CDumpContext & AFXAPI<( CDumpContext& dc, cdumpcontext&=""></( CDumpContext& dc,>  
    COleSafeArray & saSrc);
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
void PtrOfIndex (long* rgIndices, void** ppvData);
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
void PutElement (long* rgIndices, void* pvData);
```  
  
### Parameters  
 `rgIndices`  
 Pointer to an array of indexes for each dimension of the array.  
  
 `pvData`  
 Pointer to the data to assign to the array. **VT_DISPATCH**, **VT_UNKNOWN**, and `VT_BSTR` variant types are pointers and do not require another level of indirection.  
  
### Remarks  
 This function automatically calls the Windows functions [SafeArrayLock](https://msdn.microsoft.com/library/windows/desktop/ms221492.aspx) and [SafeArrayUnlock](https://msdn.microsoft.com/library/windows/desktop/ms221246.aspx) before and after assigning the element. If the data element is a string, object, or variant, the function copies it correctly, and if the existing element is a string, object, or variant, it is cleared correctly.  
  
 Note that you can have multiple locks on an array, so you can put elements into an array while the array is locked by other operations.  
  
 On error, the function throws a [CMemoryException](../../mfc/reference/cmemoryexception-class.md) or [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
 [!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]  
  
##  <a name="redim"></a>  COleSafeArray::Redim  
 Changes the least significant (rightmost) bound of a safe array.  
  
```  
void Redim (SAFEARRAYBOUND * psaboundNew);
```  
  
### Parameters  
 *psaboundNew*  
 Pointer to a new safe array bound structure containing the new array bound. Only the least significant dimension of an array may be changed.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim  
 Changes the number of elements in a one-dimensional `COleSafeArray` object.  
  
```  
void ResizeOneDim (DWORD dwElements);
```  
  
### Parameters  
 `dwElements`  
 Number of elements in the one-dimensional safe array.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData  
 Decrements the lock count of an array and invalidates the pointer retrieved by `AccessData`.  
  
```  
void UnaccessData();
```  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="unlock"></a>  COleSafeArray::Unlock  
 Decrements the lock count of an array so it can be freed or resized.  
  
```  
void Unlock();
```  
  
### Remarks  
 This function is called after access to the data in an array is finished. On error, it throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
## See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)

