---
title: "ICommandPropertiesImpl::SetProperties | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
dev_langs:
- C++
helpviewer_keywords:
- SetProperties method
ms.assetid: c42132bb-16a9-4e00-aba6-dee785a98488
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8e717c1243ef0c1feea90fe70a6f1157794c0f9a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="icommandpropertiesimplsetproperties"></a>ICommandPropertiesImpl::SetProperties
Задает свойства для объекта команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommandProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms711497.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)   
 [ICommandPropertiesImpl::GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)