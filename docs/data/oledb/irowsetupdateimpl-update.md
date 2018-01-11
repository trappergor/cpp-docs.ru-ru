---
title: "IRowsetUpdateImpl::Update | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
dev_langs: C++
helpviewer_keywords: Update method
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2cf0b2989fabda9217abd64aef485f94b2c5ccc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplupdate"></a>IRowsetUpdateImpl::Update
Передает любые изменения, внесенные в строку с момента последней выборки или обновления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD ( Update )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hReserved`  
 [in] Соответствует `hChapter` параметр в [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx).  
  
 Другие параметры в разделе [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Изменения передаются путем вызова [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md). Пользователь должен вызвать [CRowset::Update](../../data/oledb/crowset-update.md) чтобы изменения вступили в силу. Задать *prgRowstatus* соответствующее значение, как описано в статье [состояния строк](https://msdn.microsoft.com/en-us/library/ms722752.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)