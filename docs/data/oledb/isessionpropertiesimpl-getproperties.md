---
title: "ISessionPropertiesImpl::GetProperties | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
dev_langs: C++
helpviewer_keywords: GetProperties method
ms.assetid: 48726c2a-9599-4fc5-9940-a932faef91ab
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 44e708420162235164355a25e5ec8f8714b4fbf0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="isessionpropertiesimplgetproperties"></a>ISessionPropertiesImpl::GetProperties
Возвращает список свойств в **DBPROPSET_SESSION** группа свойств, заданных в настоящее время в сеансе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets    
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ISessionProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms723643.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)   
 [ISessionPropertiesImpl::SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)