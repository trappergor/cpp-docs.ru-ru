---
title: "ICommandImpl::GetDBSession | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
dev_langs: C++
helpviewer_keywords: GetDBSession method
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb4a4f378d1446e722404a76a19d592a9eed0e20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="icommandimplgetdbsession"></a>ICommandImpl::GetDBSession
Возвращает указатель на интерфейс для сеанса, создавшего команду.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD (GetDBSession) (  
   REFIID riid,  
   IUnknown** ppSession   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Это полезно для получения свойств из сеанса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ICommandImpl](../../data/oledb/icommandimpl-class.md)