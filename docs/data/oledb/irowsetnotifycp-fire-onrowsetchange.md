---
title: IRowsetNotifyCP::Fire_OnRowsetChange | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- Fire_OnRowsetChange method
ms.assetid: 412a9ec2-5041-4c56-acda-dc8f8e9b35f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a46879cb301f0140993834021eeaf2bda99b4379
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101998"
---
# <a name="irowsetnotifycpfireonrowsetchange"></a>IRowsetNotifyCP::Fire_OnRowsetChange
Осуществляет широковещательную рассылку [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) событий все прослушиватели в точке подключения **IID_IRowsetNotify** известить пользователями изменений, влияющих на весь набор строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)