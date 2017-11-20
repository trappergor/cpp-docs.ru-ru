---
title: "IRowsetUpdateImpl::SetData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
dev_langs: C++
helpviewer_keywords: SetData method
ms.assetid: 7288a8d1-a7cf-4957-b832-0f3b18fd0da4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e098db995bad0d99e47d6108436a5324d2920e9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetupdateimplsetdata"></a>IRowsetUpdateImpl::SetData
Задает значения данных в одном или нескольких столбцах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD ( SetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetChange::SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Этот метод переопределяет [IRowsetChangeImpl::SetData](../../data/oledb/irowsetchangeimpl-setdata.md) метод но включает кэширование исходных данных для немедленно обновляемых подписок или Отложенная обработка операции разрешения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)