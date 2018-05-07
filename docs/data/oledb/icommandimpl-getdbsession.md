---
title: ICommandImpl::GetDBSession | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
dev_langs:
- C++
helpviewer_keywords:
- GetDBSession method
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 116838ebb5857d5761b9d58d4f84e315de56d240
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icommandimplgetdbsession"></a>ICommandImpl::GetDBSession
Возвращает указатель на интерфейс для сеанса, создавшего команду.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (GetDBSession) (REFIID riid,  
   IUnknown** ppSession);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Это полезно для получения свойств из сеанса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ICommandImpl](../../data/oledb/icommandimpl-class.md)