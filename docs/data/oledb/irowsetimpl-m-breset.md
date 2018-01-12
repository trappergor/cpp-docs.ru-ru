---
title: "IRowsetImpl::m_bReset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs: C++
helpviewer_keywords: m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4cd9840b37157aed050bb71d48a275efd2849035
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
Флаг, используемый для определения, если позиция курсора определяется в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Если потребитель вызывает метод [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) с отрицательным значением `lOffset` или *cRows* и `m_bReset` имеет значение true, `GetNextRows` перемещается в конец набора строк. Если `m_bReset` имеет значение false, потребитель получает код ошибки в соответствии со спецификацией OLE DB. `m_bReset` Флаг получает значение **true** при первом создании набора строк и когда потребитель вызывает метод [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md). Он возвращает значение **false** при вызове `GetNextRows`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)