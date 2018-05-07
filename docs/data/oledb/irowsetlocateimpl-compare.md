---
title: IRowsetLocateImpl::Compare | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 208f912e92045daec36066e1dcc06fc38b5a8ed2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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