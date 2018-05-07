---
title: CBulkRowset::MoveToRatio | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ab702781ed47a4520b53e9698319b5c245e2dfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cbulkrowsetmovetoratio"></a>CBulkRowset::MoveToRatio
Извлекает строки, начиная с долей позиции в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nNumerator`  
 [in] Числитель, используемый для определения доли позиции, из которого требуется извлечь данные.  
  
 `nDenominator`  
 [in] Знаменатель, используемый для определения доли позиции, из которого требуется извлечь данные.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 `MoveToRatio` Извлекает строки примерно по следующей формуле:  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 Где `RowsetSize` равно размеру набора строк, измеряемый в строках. Точность по этой формуле, зависит от конкретного поставщика. Дополнительные сведения см. в разделе [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CBulkRowset](../../data/oledb/cbulkrowset-class.md)