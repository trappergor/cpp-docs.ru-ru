---
title: "CBulkRowset::MoveToBookmark | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs: C++
helpviewer_keywords: MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 883bea68992d646fd7ee82257f794394a1d2ffc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
Извлекает строку, помеченную закладки или строки с указанным смещением (`lSkip`) с этой закладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
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