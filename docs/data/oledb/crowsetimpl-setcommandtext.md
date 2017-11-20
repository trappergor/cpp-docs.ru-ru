---
title: "CRowsetImpl::SetCommandText | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
dev_langs: C++
helpviewer_keywords: SetCommandText method
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a33af61311b9c202e5e0c68579ac4f21afd98f94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetimplsetcommandtext"></a>CRowsetImpl::SetCommandText
Проверяет и сохраняет **DBID**s в двух строк ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pTableID`  
 [in] Указатель на **DBID** представляющее идентификатор таблицы.  
  
 `pIndexID`  
 [in] Указатель на **DBID** представляет идентификатор индекса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 **SetCommentText** метод вызывается методом `CreateRowset`, статический создания шаблона метод `IOpenRowsetImpl`.  
  
 Этот метод делегирует свою работу, вызвав [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) и [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) через повышенный указатель.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)