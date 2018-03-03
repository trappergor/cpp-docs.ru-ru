---
title: "CTypedPtrArray-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e08749341bd7865c89e397e36aeff3a6ccc0d71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray-класс
Предоставляет типобезопасную "программу-оболочку" для объектов класса `CPtrArray` или `CObArray`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Базовым классом класса массив типизированных указателей; должен быть классом массива ( `CObArray` или `CPtrArray`).  
  
 `TYPE`  
 Тип элементов, хранящихся в массиве базового класса.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|Добавляет новый элемент в конец массива. Размер массива увеличивается при необходимости|  
|[CTypedPtrArray::Append](#append)|Добавляет содержимое одного массива в другой конец. Размер массива увеличивается при необходимости|  
|[CTypedPtrArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|  
|[CTypedPtrArray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|  
|[CTypedPtrArray::GetAt](#getat)|Возвращает значение по указанному индексу.|  
|[CTypedPtrArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|  
|[CTypedPtrArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|  
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[[CTypedPtrArray::operator]](#operator_at)|Получает или задает элемент с указанным индексом.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `CTypedPtrArray` вместо `CPtrArray` или `CObArray`, средство проверки типов C++ позволяет избежать ошибок, вызванных типы несоответствие указателей.  
  
 Кроме того `CTypedPtrArray` оболочки выполняет большую часть приведение, требуемый при использовании `CObArray` или `CPtrArray`.  
  
 Так как все `CTypedPtrArray` функции — это встроенные, использование этого шаблона не влияет на значительно размер или скорость кода.  
  
 Дополнительные сведения об использовании `CTypedPtrArray`, см. в статьях [коллекций](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="add"></a>CTypedPtrArray::Add  
 Эта функция-член вызывает `BASE_CLASS` **:: добавить**.  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, определяющий тип элемента, добавляемого в массив.  
  
 `newElement`  
 Элемент, добавляемый в этот массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::Add](../../mfc/reference/cobarray-class.md#add).  
  
##  <a name="append"></a>CTypedPtrArray::Append  
 Эта функция-член вызывает `BASE_CLASS` **:: Append**.  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Базовым классом класса массив типизированных указателей; должен быть классом массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 *src*  
 Источник элементов, добавляемых в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс первый добавленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::Append](../../mfc/reference/cobarray-class.md#append).  
  
##  <a name="copy"></a>CTypedPtrArray::Copy  
 Эта функция-член вызывает `BASE_CLASS` **:: копирования**.  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Базовым классом класса массив типизированных указателей; должен быть классом массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 *src*  
 Источник элементов, копируемых в массив.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).  
  
##  <a name="elementat"></a>CTypedPtrArray::ElementAt  
 Это встроенная функция вызывает `BASE_CLASS` **:: ElementAt**.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, определяющий тип элементов, хранящихся в этом массиве.  
  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Временную ссылку на элемент в местоположении, заданном свойством `nIndex`. Этот элемент имеет тип, указанный в параметре шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).  
  
##  <a name="getat"></a>CTypedPtrArray::GetAt  
 Это встроенная функция вызывает `BASE_CLASS` **:: GetAt**.  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов, которые хранятся в массиве.  
  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия элемента в местоположении, заданном свойством `nIndex`. Этот элемент имеет тип, указанный в параметре шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)  
  
##  <a name="insertat"></a>CTypedPtrArray::InsertAt  
 Эта функция-член вызывает `BASE_CLASS` **:: InsertAt**.  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    TYPE newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целое значение индекса, может быть больше, чем значение, возвращаемое [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 `newElement`  
 Указатель на объект помещается в этот массив. Объект `newElement` значения **NULL** разрешено.  
  
 `nCount`  
 Количество раз, когда этот элемент должен быть вставлен (по умолчанию-1).  
  
 `nStartIndex`  
 Целое значение индекса, может быть больше, чем значение, возвращаемое `CObArray::GetUpperBound`.  
  
 `BASE_CLASS`  
 Базовым классом класса массив типизированных указателей; должен быть классом массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 `pNewArray`  
 Другой массив, содержащий элементы для добавления в этот массив.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).  
  
##  <a name="operator_at"></a>[CTypedPtrArray::operator]  
 Эти операторы встроенного вызова `BASE_CLASS` **:: operator []**.  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов, которые хранятся в массиве.  
  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор вызывается для массивов, которые не являются **const**, можно использовать в правом (r-значение) или (l значение) слева от оператора присваивания. Второе, вызывается для **const** массивы, может использоваться только в правой части окна.  
  
 Отладочная версия библиотеки утверждения, если индекс (либо левой или правой части оператора присваивания) выходит за границы.  
  
##  <a name="setat"></a>CTypedPtrArray::SetAt  
 Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 *ptr*  
 Указатель на элемент, вставляемый в массиве, с nIndex. Допускается значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).  
  
##  <a name="setatgrow"></a>CTypedPtrArray::SetAtGrow  
 Эта функция-член вызывает `BASE_CLASS` **:: SetAtGrow**.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0.  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 `newElement`  
 Указатель на объект для добавления в этот массив. Объект **NULL** является допустимым значением.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CPtrArray](../../mfc/reference/cptrarray-class.md)   
 [Класс CObArray](../../mfc/reference/cobarray-class.md)
