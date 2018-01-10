---
title: "CDBErrorInfo::GetErrorInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetErrorInfo
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
dev_langs: C++
helpviewer_keywords: GetErrorInfo method
ms.assetid: 234e1f02-c307-4666-b3ce-2a4d62407fa1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c97ce1d235f9107fb19c64b32df9cc9fbacab84f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfogeterrorinfo"></a>CDBErrorInfo::GetErrorInfo
Вызовы [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) для возврата [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) указатель интерфейса на указанную запись.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT GetErrorInfo(   
   ULONG ulRecordNum,   
   LCID lcid,   
   IErrorInfo** ppErrorInfo    
) const throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) в *справочника программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)