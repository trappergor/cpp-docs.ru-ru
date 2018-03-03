---
title: "Класс COleSafeArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 39c7a471b5c397c430f419514b9ebf1d4da62f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
|[COleSafeArray::Attach](#attach)|Обеспечивает контроль существующего **VARIANT** массив `COleSafeArray` объекта.|  
|[COleSafeArray::Clear](#clear)|Освобождает все данные в базовых **VARIANT**.|  
|[COleSafeArray::Copy](#copy)|Создает копию существующего массива.|  
|[COleSafeArray::Create](#create)|Создает безопасный массив.|  
|[COleSafeArray::CreateOneDim](#createonedim)|Создает одномерный массив `COleSafeArray` объекта.|  
|[COleSafeArray::Destroy](#destroy)|Удаляет существующего массива.|  
|[COleSafeArray::DestroyData](#destroydata)|Удаляет данные в безопасном массиве.|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Уничтожает дескриптор безопасного массива.|  
|[COleSafeArray::Detach](#detach)|Отсоединяет **VARIANT** массива из `COleSafeArray` (таким образом, данные не будут освобождены).|  
|[COleSafeArray::GetByteArray](#getbytearray)|Копирует содержимое безопасного массива в [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](#getdim)|Возвращает число измерений в массиве.|  
|[COleSafeArray::GetElement](#getelement)|Получает один элемент безопасного массива.|  
|[COleSafeArray::GetElemSize](#getelemsize)|Возвращает размер в байтах, из одного элемента в безопасном массиве.|  
|[COleSafeArray::GetLBound](#getlbound)|Возвращает нижнюю границу любого измерения безопасного массива.|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Возвращает количество элементов в одномерном массиве `COleSafeArray` объекта.|  
|[COleSafeArray::GetUBound](#getubound)|Возвращает верхнюю границу любого измерения безопасного массива.|  
|[COleSafeArray::Lock](#lock)|Увеличивает счетчик блокировки массива и размещает указатель на данные массива в дескрипторе массива.|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Возвращает указатель индексированного элемента.|  
|[COleSafeArray::PutElement](#putelement)|Помещает в массив один элемент.|  
|[COleSafeArray::Redim](#redim)|Изменяет значение младших (крайний справа) границы безопасного массива.|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Изменяет количество элементов в одномерном массиве `COleSafeArray` объекта.|  
|[COleSafeArray::UnaccessData](#unaccessdata)|Уменьшает блокировку count массива и делает недействительным указатель извлекается с `AccessData`.|  
|[COleSafeArray::Unlock](#unlock)|Уменьшает счетчик блокировок в массиве так, чтобы освободить или изменения размера.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Получает доступ к базовым **VARIANT** структуры `COleSafeArray` объекта.|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Получает доступ к базовым **VARIANT** структуры `COleSafeArray` объекта.|  
|[COleSafeArray::operator =](#operator_eq)|Копирует значения в `COleSafeArray` объекта ( **SAFEARRAY**, **VARIANT**, `COleVariant`, или `COleSafeArray` массива).|  
|[COleSafeArray::operator ==](#operator_eq_eq)|Сравнивает два массива типа variant ( **SAFEARRAY**, **VARIANT**, `COleVariant`, или `COleSafeArray` массивы).|  
|[COleSafeArray::operator&lt;&lt;](#operator_lt_lt)|Выводит содержимое `COleSafeArray` объекта в контекст дампа.|  
  
## <a name="remarks"></a>Примечания  
 `COleSafeArray`является производным от OLE **VARIANT** структуры. OLE **SAFEARRAY** функции-члены доступны через `COleSafeArray`, а также как набор функций-членов специально для одномерных массивов байтов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="accessdata"></a>COleSafeArray::AccessData  
 Извлекает указатель на данные массива.  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>Параметры  
 `ppvData`  
 Указатель на указатель на данные массива.  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="allocdata"></a>COleSafeArray::AllocData  
 Выделяет память для безопасного массива.  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor  
 Выделяет память для дескриптора безопасного массива.  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDims`  
 Число измерений в безопасном массиве.  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="attach"></a>COleSafeArray::Attach  
 Обеспечивает контроль данных в существующем **VARIANT** массив `COleSafeArray` объекта.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *varSrc*  
 Объект **VARIANT** объекта. *VarSrc* параметр должен иметь [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**VT_ARRAY**.  
  
### <a name="remarks"></a>Примечания  
 Источник **VARIANT**тип равен `VT_EMPTY`. Эта функция очищает текущие данные массива, если таковые имеются.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="clear"></a>COleSafeArray::Clear  
 Очищает безопасного массива.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Функция очищает безопасный массив, задав `VARTYPE` объекта `VT_EMPTY`. Текущее содержимое освобождаются и освобождается массив.  
  
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
 Существующий **VARIANT** или `COleVariant` скопировать в новый объект `COleSafeArray` объекта.  
  
 `pSrc`  
 Указатель на **VARIANT** скопировать в новый объект `COleSafeArray` объекта.  
  
### <a name="remarks"></a>Примечания  
 Все эти конструкторы создавать новые `COleSafeArray` объектов. Если параметр не пустой `COleSafeArray` создается объект ( `VT_EMPTY`). Если `COleSafeArray` копируется из другого массива которого [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) известен неявно ( `COleSafeArray`, `COleVariant`, или **VARIANT**), **VARTYPE** из исходный массив сохраняется и не обязательно. Если `COleSafeArray` копируется из другого массива которого **VARTYPE** неизвестен ( **SAFEARRAY**), **VARTYPE** должно быть указано в `vtSrc` параметра.  
  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="copy"></a>COleSafeArray::Copy  
 Создает копию существующего безопасного массива.  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>Параметры  
 *ppsa*  
 Указатель на расположение, в которую будет возвращен новый дескриптор массива.  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
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
 Базовый тип массива (то есть **VARTYPE** каждого элемента массива). **VARTYPE** предназначен только для подмножества типов variant. Ни **VT_ARRAY** ни **VT_BYREF** может быть установлен флаг. `VT_EMPTY`и **VT_NULL** не являются допустимым базовых типов для массива. Все другие типы являются допустимыми.  
  
 `dwDims`  
 Число измерений в массиве. Это можно изменить после создания массива с [Redim](#redim).  
  
 *rgElements*  
 Указатель на массив из количества элементов для каждого измерения в массиве.  
  
 *rgsabounds*  
 Указатель на объект vector границы (по одному для каждого измерения) для выделения для массива.  
  
### <a name="remarks"></a>Примечания  
 Эта функция очистит текущего массива данных, при необходимости. В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
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
 Базовый тип массива (то есть **VARTYPE** каждого элемента массива).  
  
 `dwElements`  
 Число элементов в массиве. Это можно изменить после создания массива с [ResizeOneDim](#resizeonedim).  
  
 `pvSrcData`  
 Указатель на данные, копируемые в массив.  
  
 *nLBound*  
 Нижняя граница массива.  
  
### <a name="remarks"></a>Примечания  
 Функция выделяет и инициализирует данные для массива, копирование указанные данные, если указатель `pvSrcData` не **NULL**.  
  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="destroy"></a>COleSafeArray::Destroy  
 Уничтожает дескриптор существующего массива и все данные в массиве.  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>Примечания  
 Если объекты хранятся в массиве, каждый объект освобождается. В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydata"></a>COleSafeArray::DestroyData  
 Удаляет все данные в безопасном массиве.  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>Примечания  
 Если объекты хранятся в массиве, каждый объект освобождается. В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor  
 Уничтожает дескриптор безопасного массива.  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="detach"></a>COleSafeArray::Detach  
 Отсоединяет **VARIANT** данные из `COleSafeArray` объекта.  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовый **VARIANT** значение в `COleSafeArray` объекта.  
  
### <a name="remarks"></a>Примечания  
 Функция отсоединяет данные в безопасном массиве, задав [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) объекта `VT_EMPTY`. Это вызывающим освободить массив путем вызова функции Windows [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835).  
  
 В случае ошибки, функция создает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [COleSafeArray::PutElement](#putelement).  
  
##  <a name="getbytearray"></a>COleSafeArray::GetByteArray  
 Копирует содержимое безопасного массива в `CByteArray`.  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Параметры  
 `bytes`  
 Ссылку на [CByteArray](../../mfc/reference/cbytearray-class.md) объекта.  
  
##  <a name="getdim"></a>COleSafeArray::GetDim  
 Возвращает число измерений в `COleSafeArray` объекта.  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число измерений в безопасном массиве.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="getelement"></a>COleSafeArray::GetElement  
 Получает один элемент безопасного массива.  
  
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
 Эта функция автоматически вызывает функции windows `SafeArrayLock` и `SafeArrayUnlock` до и после получения элемента. Если элемент данных является строка, объект или вариант, функция копирует элемент в правильный порядок. Параметр `pvData` должен указывать на масштабное достаточно буфер содержит элемент.  
  
 В случае ошибки, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="getelemsize"></a>COleSafeArray::GetElemSize  
 Получает размер элемента в `COleSafeArray` объекта.  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в байтах элементов безопасного массива.  
  
##  <a name="getlbound"></a>COleSafeArray::GetLBound  
 Возвращает нижнюю границу любого измерения `COleSafeArray` объекта.  
  
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
 В случае ошибки, функция создает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="getonedimsize"></a>COleSafeArray::GetOneDimSize  
 Возвращает количество элементов в одномерном массиве `COleSafeArray` объекта.  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в одномерном массиве безопасным.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="getubound"></a>COleSafeArray::GetUBound  
 Возвращает верхнюю границу любого измерения безопасного массива.  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDim`  
 Измерение массива, для которого необходимо получить значение верхней границы.  
  
 *pUBound*  
 Указатель на расположение, чтобы вернуть значение верхней границы.  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, функция создает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="lock"></a>COleSafeArray::Lock  
 Увеличивает счетчик блокировки массиве и поместить указатель на данные массива в дескрипторе массива.  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, он выдает [COleException](../../mfc/reference/coleexception-class.md).  
  
 Указатель в массиве дескрипторов действителен `Unlock` вызывается. Вызовы `Lock` могут быть вложенными; равно числу вызовов `Unlock` являются обязательными.  
  
 При ее нельзя удалить массив.  
  
##  <a name="operator_lpcvariant"></a>COleSafeArray::operator LPCVARIANT  
 Вызовите этот оператор приведения для доступа к базовым **VARIANT** структуры для этого `COleSafeArray` объекта.  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="operator_lpvariant"></a>COleSafeArray::operator LPVARIANT  
 Вызовите этот оператор приведения для доступа к базовым **VARIANT** структуры для этого `COleSafeArray` объекта.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что изменение значения в **VARIANT** структуры обращаются указатель, возвращаемый этой функцией изменит значение этой `COleSafeArray` объекта.  
  
##  <a name="operator_eq"></a>COleSafeArray::operator =  
 Эти перегруженных операторах присваивания копирования исходного значения в это `COleSafeArray` объекта.  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Примечания  
 Краткое описание каждого оператора выглядит следующим образом:  
  
- **оператор = (** *saSrc* **)** копирует существующий `COleSafeArray` объект в этот объект.  
  
- **оператор = (** *varSrc***)** копирует существующий **VARIANT** или `COleVariant` массив в этот объект.  
  
- **оператор = (** `pSrc` **)** копии **VARIANT** объект массива осуществляется `pSrc` в этот объект.  
  
##  <a name="operator_eq_eq"></a>COleSafeArray::operator ==  
 Этот оператор сравнивает два массива ( **SAFEARRAY**, **VARIANT**, `COleVariant`, или `COleSafeArray` массивы) и возвращает ненулевое значение, если объекты равны; в противном случае — 0.  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
Оператор CDumpContext & AFXAPI << (CDumpContext & контроллера домена,  
    COleSafeArray и saSrc);
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
void PtrOfIndex (long * rgIndices,  
    void ** ppvData);
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
void PutElement (long * rgIndices,  
    void * pvData);
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
