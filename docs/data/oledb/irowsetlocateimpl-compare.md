---
title: "IRowsetLocateImpl::Compare | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57cef167c76d3cfe2396684ddb4ba5959ef38e5c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetlocateimplcompare"></a>IRowsetLocateImpl::Compare
Сравнивает две закладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (Compare )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Одно из закладки может быть стандартной определяемых OLE DB [Стандартная закладка](https://msdn.microsoft.com/en-us/library/ms712954.aspx) (**DBBMK_FIRST**, **DBBMK_LAST**, или **DBBMK_INVALID**). Значение, возвращаемое в `pComparison` показывает связь между двумя закладки:  
  
-   **DBCOMPARE_LT** (`cbBookmark1` перед `cbBookmark2`.)  
  
-   **DBCOMPARE_EQ** (`cbBookmark1` равен `cbBookmark2`.)  
  
-   **DBCOMPARE_GT** (`cbBookmark1` после `cbBookmark2`.)  
  
-   **DBCOMPARE_NE** (закладки, равно и не упорядоченными.)  
  
-   **DBCOMPARE_NOTCOMPARABLE** (нельзя сравнивать закладки.)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)