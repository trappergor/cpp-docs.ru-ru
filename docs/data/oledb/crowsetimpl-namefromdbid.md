---
title: "CRowsetImpl::NameFromDBID | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
dev_langs: C++
helpviewer_keywords: NameFromDBID method
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afe16dfefa719760c998c25cc107ba99caacff84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimplnamefromdbid"></a>CRowsetImpl::NameFromDBID
Извлекает строку из **DBID** и копирует его в `bstr` переданный.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *pDBID*  
 [in] Указатель на **DBID** из которого извлекается строка.  
  
 `bstr`  
 [in] Объект [CComBSTR](../../atl/reference/ccombstr-class.md) ссылку на поместите копию **DBID** строки.  
  
 `bIndex`  
 [in] **true** индекс **DBID**; **false** Если таблицы **DBID**.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`. В зависимости от того, следует ли **DBID** является таблица или индекс (обозначается `bIndex`), метод будет либо возвращают **значение DB_E_NOINDEX** или **DB_E_NOTABLE**.  
  
## <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `CRowsetImpl` реализации [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) и [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)