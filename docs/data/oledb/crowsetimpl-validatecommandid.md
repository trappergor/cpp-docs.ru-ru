---
title: CRowsetImpl::ValidateCommandID | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
dev_langs:
- C++
helpviewer_keywords:
- ValidateCommandID method
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b83f0e8bb65a6043a9ca48f87ffe8babfb73e22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098502"
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