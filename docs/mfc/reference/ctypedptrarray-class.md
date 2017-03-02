---
title: "CTypedPtrArray-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrArray
dev_langs:
- C++
helpviewer_keywords:
- pointer arrays
- CTypedPtrArray class
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
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
ms.openlocfilehash: 24b21d017d46cc88d7e243aff75ccf6383d2c870
ms.lasthandoff: 02/24/2017

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
 Базовый класс для класса array типизированный указатель; должен быть классом массива ( `CObArray` или `CPtrArray`).  
  
 `TYPE`  
 Тип элементов, хранящихся в массиве базового класса.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|Добавляет новый элемент в конец массива. Размер массива увеличивается при необходимости|  
|[CTypedPtrArray::Append](#append)|Добавляет содержимое одного массива в конец другого. Размер массива увеличивается при необходимости|  
|[CTypedPtrArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|  
|[CTypedPtrArray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|  
|[CTypedPtrArray::GetAt](#getat)|Возвращает значение по указанному индексу.|  
|[CTypedPtrArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|  
|[CTypedPtrArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|  
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CTypedPtrArray::operator]](#operator_at)|Получает или задает элемент с указанным индексом.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `CTypedPtrArray` вместо `CPtrArray` или `CObArray`, средство проверки типов C++ позволяет избежать ошибок, вызванных указатель несовпадающие типы.  
  
 Кроме того `CTypedPtrArray` оболочка выполняет большую часть приведения, которое было бы необходимо при использовании `CObArray` или `CPtrArray`.  
  
 Так как все `CTypedPtrArray` функций, встроенных, этот шаблон не влияет на значительно размер или скорость кода.  
  
 Дополнительные сведения об использовании `CTypedPtrArray`, см. в статьях [коллекции](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="a-nameadda--ctypedptrarrayadd"></a><a name="add"></a>CTypedPtrArray::Add  
 Эта функция-член вызывает `BASE_CLASS` **:: добавить**.  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элемента, добавляемого в массив.  
  
 `newElement`  
 Элемент, добавляемый в этот массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::Add](../../mfc/reference/cobarray-class.md#add).  
  
##  <a name="a-nameappenda--ctypedptrarrayappend"></a><a name="append"></a>CTypedPtrArray::Append  
 Эта функция-член вызывает `BASE_CLASS` **:: Append**.  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Базовый класс для класса array типизированный указатель; должен быть классом массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 *src*  
 Источник элементов, добавляемый в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс первый добавленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::Append](../../mfc/reference/cobarray-class.md#append).  
  
##  <a name="a-namecopya--ctypedptrarraycopy"></a><a name="copy"></a>CTypedPtrArray::Copy  
 Эта функция-член вызывает `BASE_CLASS` **:: Копировать**.  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Базовый класс для класса array типизированный указатель; должен быть классом массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 *src*  
 Источник копируемых в массив элементов.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).  
  
##  <a name="a-nameelementata--ctypedptrarrayelementat"></a><a name="elementat"></a>CTypedPtrArray::ElementAt  
 Это встроенная функция вызывает `BASE_CLASS` **:: ElementAt**.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, хранящихся в этом массиве.  
  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Временную ссылку на элемент в местоположении, заданном свойством `nIndex`. Этот элемент имеет тип, указанный параметром шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).  
  
##  <a name="a-namegetata--ctypedptrarraygetat"></a><a name="getat"></a>CTypedPtrArray::GetAt  
 Это встроенная функция вызывает `BASE_CLASS` **:: GetAt**.  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, которые хранятся в массиве.  
  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия элемента в расположении, указанном в `nIndex`. Этот элемент имеет тип, указанный параметром шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)  
  
##  <a name="a-nameinsertata--ctypedptrarrayinsertat"></a><a name="insertat"></a>CTypedPtrArray::InsertAt  
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
 Количество раз, когда этот элемент должен быть вставлен (по умолчанию 1).  
  
 `nStartIndex`  
 Целое значение индекса, может быть больше, чем значение, возвращаемое `CObArray::GetUpperBound`.  
  
 `BASE_CLASS`  
 Базовый класс для класса array типизированный указатель; должен быть классом массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 `pNewArray`  
 Другой массив, содержащий элементы для добавления в этот массив.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).  
  
##  <a name="a-nameoperatorata--ctypedptrarrayoperator--"></a><a name="operator_at"></a>[CTypedPtrArray::operator]  
 Эти операторы встроенный вызов `BASE_CLASS` **:: operator []**.  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, которые хранятся в массиве.  
  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор вызывается для массивов, которые не **const**, можно использовать на правом (r-значение) или (l значение) слева от оператора присваивания. Второй, вызывается для **const** массивов, может использоваться только справа.  
  
 Отладочная версия библиотеки утверждает, если индекс (либо слева или справа от оператора присваивания) выходит за допустимые пределы.  
  
##  <a name="a-namesetata--ctypedptrarraysetat"></a><a name="setat"></a>CTypedPtrArray::SetAt  
 Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *ТИП*  
 Тип элементов, хранящихся в массиве базового класса.  
  
 *PTR*  
 Указатель на элемент, который вставлен в массиве, с nIndex. Допускается значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).  
  
##  <a name="a-namesetatgrowa--ctypedptrarraysetatgrow"></a><a name="setatgrow"></a>CTypedPtrArray::SetAtGrow  
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
 Указатель на объект для добавления в этот массив. Объект **NULL** допустимое значение.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC сбор данных](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CPtrArray](../../mfc/reference/cptrarray-class.md)   
 [Класс CObArray](../../mfc/reference/cobarray-class.md)

