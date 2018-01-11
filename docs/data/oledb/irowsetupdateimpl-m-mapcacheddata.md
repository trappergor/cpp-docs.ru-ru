---
title: "IRowsetUpdateImpl::m_mapCachedData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs: C++
helpviewer_keywords: m_mapCachedData
ms.assetid: 65131743-8580-48c8-bb22-68f17c9dfa13
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c3b48a309d10d232eb311b66602e61ff727cdef7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplmmapcacheddata"></a>IRowsetUpdateImpl::m_mapCachedData
Сопоставление с исходными данными для отложенной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### <a name="parameters"></a>Параметры  
 `hRow`  
 Дескриптор строки данных.  
  
 `pData`  
 Указатель для кэширования данных. Данные имеют тип *хранения* (класс записей пользователя). В разделе *хранения* аргумента шаблона в [класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)