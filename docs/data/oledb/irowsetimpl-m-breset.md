---
title: IRowsetImpl::m_bReset | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs:
- C++
helpviewer_keywords:
- m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9aec38e3cf7e9a58c4fe99d06f35ae55cfdf81c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
Флаг, используемый для определения, если позиция курсора определяется в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Если потребитель вызывает метод [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) с отрицательным значением `lOffset` или *cRows* и `m_bReset` имеет значение true, `GetNextRows` перемещается в конец набора строк. Если `m_bReset` имеет значение false, потребитель получает код ошибки в соответствии со спецификацией OLE DB. `m_bReset` Флаг получает значение **true** при первом создании набора строк и когда потребитель вызывает метод [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md). Он возвращает значение **false** при вызове `GetNextRows`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)