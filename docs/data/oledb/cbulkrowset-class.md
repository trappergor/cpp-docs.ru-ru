---
title: Класс CBulkRowset | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
- CBulkRowset::AddRefRows
- AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset<TAccessor>.CBulkRowset
- ATL::CBulkRowset::CBulkRowset
- CBulkRowset.CBulkRowset
- CBulkRowset::CBulkRowset
- ATL.CBulkRowset.CBulkRowset
- ATL::CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset
- ATL.CBulkRowset.MoveFirst
- CBulkRowset<TAccessor>.MoveFirst
- ATL.CBulkRowset<TAccessor>.MoveFirst
- ATL::CBulkRowset::MoveFirst
- ATL::CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset::MoveFirst
- CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset.MoveFirst
- CBulkRowset.MoveLast
- ATL.CBulkRowset.MoveLast
- ATL::CBulkRowset<TAccessor>::MoveLast
- CBulkRowset::MoveLast
- CBulkRowset<TAccessor>.MoveLast
- ATL::CBulkRowset::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveLast
- CBulkRowset<TAccessor>::MoveLast
- MoveLast
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
- CBulkRowset::MovePrev
- MovePrev
- CBulkRowset<TAccessor>::MovePrev
- ATL::CBulkRowset<TAccessor>::MovePrev
- CBulkRowset<TAccessor>.MovePrev
- ATL::CBulkRowset::MovePrev
- CBulkRowset.MovePrev
- ATL.CBulkRowset.MovePrev
- ATL.CBulkRowset<TAccessor>.MovePrev
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
- ReleaseRows
- ATL.CBulkRowset<TAccessor>.ReleaseRows
- ATL::CBulkRowset<TAccessor>::ReleaseRows
- ATL.CBulkRowset.ReleaseRows
- CBulkRowset<TAccessor>::ReleaseRows
- ATL::CBulkRowset::ReleaseRows
- CBulkRowset::ReleaseRows
- CBulkRowset.ReleaseRows
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
dev_langs:
- C++
helpviewer_keywords:
- CBulkRowset class
- AddRefRows method
- CBulkRowset class, constructor
- MoveFirst method
- MoveLast method
- MoveNext method
- MovePrev method
- MoveToBookmark method
- MoveToRatio method
- ReleaseRows method
- SetRows method
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e741055950449ea07c719cf6cd4c33a34d6f43b3
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572864"
---
# <a name="cbulkrowset-class"></a>Класс CBulkRowset
Извлекает и управляет строк, чтобы работать с данными в пакетном режиме, получая несколько дескрипторов строк с помощью одного вызова.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
### <a name="parameters"></a>Параметры  
 *TAccessor*  
 Класс, метод доступа.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddRefRows](#addrefrows)|Увеличивает счетчик ссылок.|  
|[CBulkRowset](#cbulkrowset)|Конструктор.|  
|[MoveFirst](#movefirst)|Извлекает первую строку данных, выполнения новый массовой выборки при необходимости.|  
|[MoveLast](#movelast)|Переход к последней строке.|  
|[MoveNext](#movenext)|Извлекает следующую строку данных.|  
|[MovePrev](#moveprev)|Переход к предыдущей строке.|  
|[Функции MoveToBookmark](#movetobookmark)|Получает строку, помеченную с закладкой или строки с указанным смещением из эту закладку.|  
|[MoveToRatio](#movetoratio)|Извлекает строки, начиная с долей позиции в наборе строк.|  
|[ReleaseRows](#releaserows)|Задает текущую строку (`m_nCurrentRow`) и выпуски все строки.|  
|[SetRows](#setrows)|Задает число дескрипторов строк, извлекаемых в одном вызове.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование `CBulkRowset` класса.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  

## <a name="addrefrows"></a> CBulkRowset::AddRefRows
Вызовы [IRowset::AddRefRows](/previous-versions/windows/desktop/ms719619\(v=vs.85\)) следует выполнить приращение счетчика ссылок для всех строк, в данный момент получить из набора строк bulk.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT AddRefRows() throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT. 
  
## <a name="cbulkrowset"></a> CBulkRowset::CBulkRowset
Создает новый `CBulkRowset` и устанавливает количество строк по умолчанию до 10.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CBulkRowset();  
```  

## <a name="movefirst"></a> CBulkRowset::MoveFirst
Извлекает первую строку данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MoveFirst() throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.

## <a name="movelast"></a> CBulkRowset::MoveLast
Переход к последней строке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MoveLast() throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="movenext"></a> CBulkRowset::MoveNext
Извлекает следующую строку данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MoveNext() throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT. Возвращает DB_S_ENDOFROWSET, по достижении конца набора строк. 

## <a name="moveprev"></a> CBulkRowset::MovePrev
Переход к предыдущей строке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MovePrev() throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="movetobookmark"></a> CBulkRowset::MoveToBookmark
Выбирается строка, помеченная закладку или строки с указанным смещением (*lSkip*) из этой закладки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark, 
   DBCOUNTITEM lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *Закладка*  
 [in] Закладка, расположения, из которого требуется извлечь данные.  
  
 *lSkip*  
 [in] Число строк из закладки в строку. Если *lSkip* равен нулю, первая строка выборки представляет строке с закладкой. Если *lSkip* -1, первый выбранная строка является строкой после строке с закладкой. Если *lSkip* равно -1, первая строка выборки представляет закладками строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в разделе [IRowset::GetData](/previous-versions/windows/desktop/ms716988\(v=vs.85\)) в *справочнике программиста OLE DB*. 

## <a name="movetoratio"></a> CBulkRowset::MoveToRatio
Извлекает строки, начиная с долей позиции в наборе строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MoveToRatio(DBCOUNTITEM nNumerator, 
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nNumerator*  
 [in] Числитель, используемый для определения доли положение, с которого для выборки данных.  
  
 *nDenominator*  
 [in] Знаменатель, используемый для определения доли положение, с которого для выборки данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `MoveToRatio` Извлекает строки, примерно по следующей формуле:  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 Где `RowsetSize` — это размер набора строк, измеряется строками. Точность по этой формуле, зависит от определенного поставщика. Дополнительные сведения см. в разделе [IRowsetScroll::GetRowsAtRatio](/previous-versions/windows/desktop/ms709602\(v=vs.85\)) в *Справочник программиста OLE DB по*.   

## <a name="releaserows"></a> CBulkRowset::ReleaseRows
Вызовы [IRowset::ReleaseRows](/previous-versions/windows/desktop/ms719771\(v=vs.85\)) для уменьшения числа ссылок для всех строк, в данный момент получить из набора строк bulk.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT ReleaseRows() throw();   
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="setrows"></a> CBulkRowset::SetRows
Задает количество дескрипторов строки, полученные при каждом вызове.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void SetRows(DBROWCOUNT nRows) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nRows*  
 [in] Новый размер набора строк (количество строк).  
  
### <a name="remarks"></a>Примечания  
 Если вы вызываете эту функцию, он должен быть перед открытием набора строк.
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)