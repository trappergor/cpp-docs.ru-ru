---
title: "CDynamicParameterAccessor::GetParamStatus | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
dev_langs: C++
helpviewer_keywords: GetParamStatus method
ms.assetid: 9300225a-616c-4a7d-82d0-8c2ecd4d8185
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 483a6b8aea87d552d1397f70222323fbe8514747
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessorgetparamstatus"></a>CDynamicParameterAccessor::GetParamStatus
Получает состояние указанного параметра, сохраненного в буфере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      bool GetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS* pStatus  
);  
DBSTATUS* GetParamStatus(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nParam`  
 [in] Номер параметра (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером — это индекс параметра, в зависимости от порядка в SQL или хранимой процедуры. В разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) в качестве примера.  
  
 `pStatus`  
 [out] Указатель на переменную, содержащую `DBSTATUS` состояние указанного параметра. Сведения о `DBSTATUS` значения, в разделе [состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в *Справочник программиста OLE DB*, или выполните поиск `DBSTATUS` в oledb.h.  
  
## <a name="remarks"></a>Примечания  
 Первый переопределить возвращает **true** в случае успешного выполнения или **false** при сбое. Второй переопределить точек памяти, содержащей состояние указанного параметра.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)