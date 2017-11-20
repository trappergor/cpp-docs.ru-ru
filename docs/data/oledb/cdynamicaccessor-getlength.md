---
title: "CDynamicAccessor::GetLength | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs: C++
helpviewer_keywords: GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d62a4d23bb25fec0f85b5230b0136b745fb0801
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
Получает длину указанного столбца.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      bool GetLength(   
   DBORDINAL nColumn,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const CHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const WCHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nColumn`  
 [in] Номер столбца. Номера столбцов начинается с 1. Значение 0 ссылается на столбец закладки в том случае, если таковые имеются.  
  
 `pColumnName`  
 [in] Указатель на символьную строку, содержащую имя столбца.  
  
 `pLength`  
 [out] Указатель на целое число со знаком, содержащее длину столбца в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при обнаружении указанного столбца. В противном случае эта функция возвращает **false**.  
  
## <a name="remarks"></a>Примечания  
 Первый переопределение принимает номер столбца и переопределения второй и третий принимают имя столбца в формате ANSI или Юникод, соответственно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)