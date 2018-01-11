---
title: "IRowsetNotifyImpl::OnRowChange | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
dev_langs: C++
helpviewer_keywords: OnRowChange method
ms.assetid: 148bee03-3707-4bbf-8c51-657efc63645f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d20e144ae700a19fb6b87820fd092bff11d3bc88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetnotifyimplonrowchange"></a>IRowsetNotifyImpl::OnRowChange
Уведомляет объект-получатель о первом изменении строки или обо всех изменениях, которые влияют на всю строку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) для описания параметров.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В разделе [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) для возврата описания значений.  
  
## <a name="remarks"></a>Примечания  
 Этот метод создает оболочку для [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) метод. В описании этого метода в справочнике программиста OLE DB сведения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx)