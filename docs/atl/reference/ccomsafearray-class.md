---
title: "Класс класса CComSafeArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeArray
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e78c0cb7a0e2fb6cc1e1ac4bba9186d4beee98b4
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafearray-class"></a>Класс CComSafeArray
Этот класс является оболочкой для структуры **SAFEARRAY** .  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных для сохранения в массиве.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Конструктор.|  
|[Класса CComSafeArray:: ~ класса CComSafeArray](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::Add](#add)|Добавляет один или несколько элементов или структуру **SAFEARRAY** в `CComSafeArray`.|  
|[CComSafeArray::Attach](#attach)|Прикрепляет структуру **SAFEARRAY** к объекту `CComSafeArray` .|  
|[CComSafeArray::CopyFrom](#copyfrom)|Копирует содержимое структуры **SAFEARRAY** в объект `CComSafeArray` .|  
|[CComSafeArray::CopyTo](#copyto)|Создает копию объекта `CComSafeArray`.|  
|[CComSafeArray::Create](#create)|Создает объект `CComSafeArray`.|  
|[CComSafeArray::Destroy](#destroy)|Уничтожает объект `CComSafeArray`.|  
|[CComSafeArray::Detach](#detach)|Отсоединяет структуру **SAFEARRAY** от объекта `CComSafeArray` .|  
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
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|Приводит значение к указателю **SAFEARRAY** .|  
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Получает элемент из массива.|  
|[CComSafeArray::operator =](#operator_eq)|Оператор присвоения.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::m_psa](#m_psa)|Этот элемент данных содержит адрес структуры **SAFEARRAY** .|  
  
## <a name="remarks"></a>Примечания  
 `CComSafeArray`предоставляет оболочку для [тип данных массива SAFEARRAY](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e) класс, делая это простой механизм для создания и управления одно - и многомерные массивы практически любого типа VARIANT поддерживается.  
  
 `CComSafeArray` упрощает передачу массивов между процессами и обеспечивает дополнительную безопасность путем проверки значений индекса массива на соответствие верхней и нижней границам.  
  
 Нижняя граница `CComSafeArray` может начинаться с любого определенного пользователем значения. Однако нижняя граница массивов, доступ к которым осуществляется через C++, должна быть равна 0. В других языках, например Visual Basic, могут использоваться другие ограничивающие значения (например, от −10 до 10).  
  
 Используйте [CComSafeArray::Create](#create) для создания `CComSafeArray` объекта, и [CComSafeArray::Destroy](#destroy) для его удаления.  
  
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
 [!code-cpp[NVC_ATL_Utilities&#75;](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="a-nameadda--ccomsafearrayadd"></a><a name="add"></a>CComSafeArray::Add  
 Добавляет один или несколько элементов или структуру **SAFEARRAY** в `CComSafeArray`.  
  
```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `psaSrc`  
 Указатель на **SAFEARRAY** объекта.  
  
 `ulCount`  
 Количество объектов, добавляемых в массив.  
  
 *pT*  
 Указатель на один или несколько объектов, добавляемый в массив.  
  
 *t*  
 Ссылка на объект, добавляемый в массив.  
  
 `bCopy`  
 Указывает, следует ли создавать копию данных. Значение по умолчанию — **TRUE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Новые объекты добавляются в конец существующего **SAFEARRAY** объекта. При добавлении объекта многомерный массив **SAFEARRAY** объекта не поддерживается. При добавлении существующего массива объектов, оба массива должны содержать элементы того же типа.  
  
 `bCopy` Флаг учитываться при элементов типа `BSTR` или **VARIANT** добавляются в массив. Значение по умолчанию **TRUE** гарантирует новую копию данных, когда элемент добавляется в массив.  
  
##  <a name="a-nameattacha--ccomsafearrayattach"></a><a name="attach"></a>CComSafeArray::Attach  
 Прикрепляет структуру **SAFEARRAY** к объекту `CComSafeArray` .  
  
```
HRESULT Attach(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `psaSrc`  
 Указатель на **SAFEARRAY** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Присоединяет **SAFEARRAY** структуру `CComSafeArray` объекта, делая ее `CComSafeArray` доступные методы.  
  
##  <a name="a-nameccomsafearraya--ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a>CComSafeArray::CComSafeArray  
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
 `bound`  
 Объект **SAFEARRAYBOUND** структуры.  
  
 `ulCount`  
 Количество элементов в массиве.  
  
 `lLBound`  
 Значение нижней границы; то есть индекс первого элемента в массиве.  
  
 `pBound`  
 Указатель на **SAFEARRAYBOUND** структуры.  
  
 `uDims`  
 Число измерений в массиве.  
  
 `saSrc`  
 Ссылку на **SAFEARRAY** структуры или `CComSafeArray` объекта. В любом случае конструктор использует эту ссылку, чтобы скопировать массива, поэтому массива не используется после создания.  
  
 `psaSrc`  
 Указатель на **SAFEARRAY** структуры. Конструктор использует данный адрес для создания копии массива, поэтому массива не используется после создания экземпляра.  
  
### <a name="remarks"></a>Примечания  
 Создает объект `CComSafeArray`.  
  
##  <a name="a-namedtora--ccomsafearrayccomsafearray"></a><a name="dtor"></a>Класса CComSafeArray:: ~ класса CComSafeArray  
 Деструктор  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="a-namecopyfroma--ccomsafearraycopyfrom"></a><a name="copyfrom"></a>CComSafeArray::CopyFrom  
 Копирует содержимое структуры **SAFEARRAY** в объект `CComSafeArray` .  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Параметры  
 `ppArray`  
 Указатель на **SAFEARRAY** для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует содержимое **SAFEARRAY** в текущий `CComSafeArray` объекта. Существующее содержимое массива заменяются.  
  
##  <a name="a-namecopytoa--ccomsafearraycopyto"></a><a name="copyto"></a>CComSafeArray::CopyTo  
 Создает копию объекта `CComSafeArray`.  
  
```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Параметры  
 `ppArray`  
 Указатель на расположение, в котором будет создан новый **SAFEARRAY**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует содержимое `CComSafeArray` объекта в **SAFEARRAY** структуры.  
  
##  <a name="a-namecreatea--ccomsafearraycreate"></a><a name="create"></a>CComSafeArray::Create  
 Создает объект `CComSafeArray`.  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pBound`  
 Указатель на **SAFEARRAYBOUND** объекта.  
  
 `uDims`  
 Число измерений в массиве.  
  
 `ulCount`  
 Количество элементов в массиве.  
  
 `lLBound`  
 Значение нижней границы; то есть индекс первого элемента в массиве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Объект `CComSafeArray` объект может быть создан из существующего **SAFEARRAYBOUND** структура и количество измерений или путем указания числа элементов в массиве и нижняя граница. Если массив является доступным с Visual C++, нижняя граница должно быть равно 0. Другие языки могут разрешить другие значения для нижней границы (например, Visual Basic поддерживает массивы с элементами в диапазоне, например 10 до 10).  
  
##  <a name="a-namedestroya--ccomsafearraydestroy"></a><a name="destroy"></a>CComSafeArray::Destroy  
 Уничтожает объект `CComSafeArray`.  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Удаляет существующий `CComSafeArray` объект и все данные, которые он содержит.  
  
##  <a name="a-namedetacha--ccomsafearraydetach"></a><a name="detach"></a>CComSafeArray::Detach  
 Отсоединяет структуру **SAFEARRAY** от объекта `CComSafeArray` .  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на **SAFEARRAY** объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отсоединяет **SAFEARRAY** объекта из `CComSafeArray` объекта.  
  
##  <a name="a-namegetata--ccomsafearraygetat"></a><a name="getat"></a>CComSafeArray::GetAt  
 Получает один элемент из одномерного массива.  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>Параметры  
 `lIndex`  
 Номер индекса в массиве для возврата значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент массива требуется.  
  
##  <a name="a-namegetcounta--ccomsafearraygetcount"></a><a name="getcount"></a>CComSafeArray::GetCount  
 Возвращает число элементов в массиве.  
  
```
ULONG GetCount(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `uDim`  
 Измерение массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число элементов в массиве.  
  
### <a name="remarks"></a>Примечания  
 При использовании с многомерного массива, этот метод возвращает количество элементов в определенное измерение.  
  
##  <a name="a-namegetdimensionsa--ccomsafearraygetdimensions"></a><a name="getdimensions"></a>CComSafeArray::GetDimensions  
 Возвращает число измерений в массиве.  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число измерений в массиве.  
  
##  <a name="a-namegetlowerbounda--ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a>CComSafeArray::GetLowerBound  
 Возвращает нижнюю границу заданного измерения массива.  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `uDim`  
 Измерение массива, для которого нужно получить нижняя граница. Если не указано, значение по умолчанию — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нижнюю границу.  
  
### <a name="remarks"></a>Примечания  
 Если нижняя граница — 0, это указывает массивом типа C, первым элементом является элемент с номером 0. В случае возникновения ошибки, например, аргумента Недопустимое измерение, этот метод вызывает метод `AtlThrow` с описанием ошибки HRESULT.  
  
##  <a name="a-namegetsafearrayptra--ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr  
 Возвращает адрес элемента данных `m_psa` .  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на [CComSafeArray::m_psa](#m_psa) данные-член.  
  
##  <a name="a-namegettypea--ccomsafearraygettype"></a><a name="gettype"></a>CComSafeArray::GetType  
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
  
##  <a name="a-namegetupperbounda--ccomsafearraygetupperbound"></a><a name="getupperbound"></a>CComSafeArray::GetUpperBound  
 Возвращает верхнюю границу любого измерения массива.  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `uDim`  
 Измерение массива, для которого необходимо получить значение верхней границы. Если не указано, значение по умолчанию — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает верхнюю границу. Это значение является включительно, максимальный допустимый индекс для этого измерения.  
  
### <a name="remarks"></a>Примечания  
 В случае возникновения ошибки, например, аргумента Недопустимое измерение, этот метод вызывает метод `AtlThrow` с описанием ошибки HRESULT.  
  
##  <a name="a-nameissizablea--ccomsafearrayissizable"></a><a name="issizable"></a>CComSafeArray::IsSizable  
 Проверяет, можно ли изменить размер объекта `CComSafeArray` .  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если `CComSafeArray` можно изменять, **false** в противном случае.  
  
##  <a name="a-namempsaa--ccomsafearraympsa"></a><a name="m_psa"></a>CComSafeArray::m_psa  
 Содержит адрес **SAFEARRAY** доступ к структуре.  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="a-namemultidimgetata--ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a>CComSafeArray::MultiDimGetAt  
 Получает один элемент из многомерного массива.  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>Параметры  
 `alIndex`  
 Указатель на объект vector индексов для каждого измерения в массиве. Левое измерение (наиболее значительному) `alIndex`[0] *.*  
  
 *t*  
 Ссылка на данные, возвращаемые.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namemultidimsetata--ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a>CComSafeArray::MultiDimSetAt  
 Задает значение элемента в многомерном массиве.  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>Параметры  
 `alIndex`  
 Указатель на объект vector индексов для каждого измерения в массиве. Правое измерение (младших) является `alIndex`[0].  
  
 *T*  
 Задает значение нового элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Это многомерный версия [CComSafeArray::SetAt](#setat).  
  
##  <a name="a-nameoperatorata--ccomsafearrayoperator-"></a><a name="operator_at"></a>CComSafeArray::operator\[\]  
 Получает элемент из массива.  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>Параметры  
 *Индекс nIndex*  
 Номер индекса обязательный элемент в массиве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает элемент, соответствующий массив.  
  
### <a name="remarks"></a>Примечания  
 Выполняет те же функции для [CComSafeArray::GetAt](#getat), однако этот оператор работает только с одномерные массивы.  
  
##  <a name="a-nameoperatoreqa--ccomsafearrayoperator-"></a><a name="operator_eq"></a>CComSafeArray::operator =  
 Оператор присвоения.  
  
```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `saSrc`  
 Ссылка на объект `CComSafeArray`.  
  
 `psaSrc`  
 Указатель на **SAFEARRAY** объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип данных, хранящихся в массиве.  
  
##  <a name="a-nameoperatorlpsafearraya--ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a>CComSafeArray::operator LPSAFEARRAY  
 Приводит значение к указателю **SAFEARRAY** .  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Приводит значение к указателю **SAFEARRAY** .  
  
##  <a name="a-nameresizea--ccomsafearrayresize"></a><a name="resize"></a>CComSafeArray::Resize  
 Изменяет размер объекта `CComSafeArray` .  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pBound`  
 Указатель на **SAFEARRAYBOUND** структуру, содержащую сведения о число элементов и нижняя граница массива.  
  
 `ulCount`  
 Запрошенное число объектов в массиве с измененным размером.  
  
 `lLBound`  
 Нижняя граница.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет только самой правой размерности. Массивы, которые возвращают размер не будет **IsResizable** как **false**.  
  
##  <a name="a-namesetata--ccomsafearraysetat"></a><a name="setat"></a>CComSafeArray::SetAt  
 Задает значение элемента в одномерном массиве.  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lIndex`  
 Индекс элемента в массиве.  
  
 *t*  
 Новое значение указанного элемента.  
  
 `bCopy`  
 Указывает, следует ли создавать копию данных. Значение по умолчанию — **TRUE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `bCopy` Флаг учитываться при элементов типа `BSTR` или **VARIANT** добавляются в массив. Значение по умолчанию **TRUE** гарантирует новую копию данных, когда элемент добавляется в массив.  
  
## <a name="see-also"></a>См. также  
 [Тип данных массива SAFEARRAY](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](#create)   
 [CComSafeArray::Destroy](#destroy)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

