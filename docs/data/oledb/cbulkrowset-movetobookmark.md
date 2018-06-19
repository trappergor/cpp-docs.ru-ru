---
title: CBulkRowset::MoveToBookmark | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs:
- C++
helpviewer_keywords:
- MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b1911fe170262e65ef06e65649f837a0b723d05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094651"
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
Извлекает строку, помеченную закладки или строки с указанным смещением (`lSkip`) с этой закладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `bookmark`  
 [in] Закладка, расположения, из которого требуется извлечь данные.  
  
 `lSkip`  
 [in] Число строк из закладки для целевой строки. Если `lSkip` равен нулю, Первая выбранная строка является строкой, закладкой. Если `lSkip` -1, Первая выбранная строка является строкой после закладкой строке. Если `lSkip` равно -1, закладкой строки является первой выбранной строки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В разделе [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CBulkRowset](../../data/oledb/cbulkrowset-class.md)