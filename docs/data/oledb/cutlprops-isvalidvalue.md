---
title: "CUtlProps::IsValidValue | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
dev_langs: C++
helpviewer_keywords: IsValidValue method
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 06193b8c560c5ac6006698813222e698a98bccc3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropsisvalidvalue"></a>CUtlProps::IsValidValue
Используется для проверки значения перед заданием свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `iCurSet`  
 Индекс в массиве набор свойств. нуль, если определено только одно свойство.  
  
 `pDBProp`  
 Идентификатор свойства и новое значение в [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) структуры.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`. Значение по умолчанию возвращаемое значение — `S_OK`.  
  
## <a name="remarks"></a>Примечания  
 Если у вас есть все процедуры проверки, необходимые для выполнения на значение, которое вы собираетесь использовать, чтобы задать свойство, должны переопределить данную функцию. Например, можно проверить **DBPROP_AUTH_PASSWORD** к таблице пароль, чтобы определить, является допустимым значением.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)