---
title: "CDynamicParameterAccessor::GetParamType | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
dev_langs: C++
helpviewer_keywords: GetParamType method
ms.assetid: d9c46775-c2a6-4100-8b69-99f13c52958b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b573265c30c0d6ec45665109ff41042e9a2f24dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorgetparamtype"></a>CDynamicParameterAccessor::GetParamType
Получает тип данных указанного параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      bool GetParamType(  
   DBORDINAL nParam,  
   DBTYPE* pType   
) const throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nParam`  
 [in] Номер параметра (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером — это индекс параметра, в зависимости от порядка в SQL или хранимой процедуры. В разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) в качестве примера.  
  
 `pType`  
 [out] Указатель на переменной, содержащей тип данных указанного параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения или **false** при сбое.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)