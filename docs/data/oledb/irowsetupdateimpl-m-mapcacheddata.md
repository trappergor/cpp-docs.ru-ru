---
title: IRowsetUpdateImpl::m_mapCachedData | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs:
- C++
helpviewer_keywords:
- m_mapCachedData
ms.assetid: 65131743-8580-48c8-bb22-68f17c9dfa13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd19f8706e50d1eefb26dadfb837d8bd4f13f061
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103259"
---
# <a name="irowsetupdateimplmmapcacheddata"></a>IRowsetUpdateImpl::m_mapCachedData
Сопоставление с исходными данными для отложенной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
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