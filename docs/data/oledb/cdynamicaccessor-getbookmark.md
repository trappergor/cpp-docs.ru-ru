---
title: CDynamicAccessor::GetBookmark | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
dev_langs:
- C++
helpviewer_keywords:
- GetBookmark method
ms.assetid: 6d0a2970-0c62-4a34-bac7-149d8e990f81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac9ea217b987f7355757fc756acc0108fca0e4a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093887"
---
# <a name="cdynamicaccessorgetbookmark"></a>CDynamicAccessor::GetBookmark
Извлекает закладки для текущей строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `pBookmark`  
 [out] Указатель на [CBookmark](../../data/oledb/cbookmark-class.md) объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 Необходимо указать **DBPROP_IRowsetLocate** для `VARIANT_TRUE` для получения закладки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)