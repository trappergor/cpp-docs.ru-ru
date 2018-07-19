---
title: CRowsetImpl::m_rgRowData | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
dev_langs:
- C++
helpviewer_keywords:
- m_rgRowData
ms.assetid: e4e75ca7-12e8-4a0b-94e8-e395c21385b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a83382727c216cfeb9f99a760ee3e755e170ec36
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097384"
---
# <a name="crowsetimplmrgrowdata"></a>CRowsetImpl::m_rgRowData
По умолчанию `CAtlArray` , templatizes от аргумента шаблона записи пользователя для `CRowsetImpl`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;  
  
```  
  
## <a name="remarks"></a>Примечания  
 **ArrayType** — параметр шаблона `CRowsetImpl`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)   
 [CRowsetImpl::m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)