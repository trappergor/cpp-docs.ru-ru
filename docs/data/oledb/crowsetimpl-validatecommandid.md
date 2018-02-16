---
title: "CRowsetImpl::ValidateCommandID | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
dev_langs:
- C++
helpviewer_keywords:
- ValidateCommandID method
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5d3b90ef56ee15e3834c2867a781323689d3054
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetimplvalidatecommandid"></a>CRowsetImpl::ValidateCommandID
Проверяет, см. Если один или оба **DBID**s содержать строковые значения и если да, копирует их членах данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pTableID`  
 [in] Указатель на **DBID** представляющее идентификатор таблицы.  
  
 `pIndexID`  
 [in] Указатель на **DBID** представляет идентификатор индекса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод вызывается через статический повышении по `CRowsetImpl` для заполнения его элементов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). По умолчанию этот метод проверяет, см. Если один или оба **DBID**s содержать строковые значения и если да, копирует их членах данных. Поместив метод при наличии этой подписи в вашей `CRowsetImpl`-производного класса, метод будет вызван вместо базовой реализации.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)