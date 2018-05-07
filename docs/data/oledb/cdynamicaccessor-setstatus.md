---
title: CDynamicAccessor::SetStatus | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
dev_langs:
- C++
helpviewer_keywords:
- SetStatus method
ms.assetid: 6db82694-e87d-4bf8-a7e3-5765cf6abff9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7bf0fd390699d83261cf52651a3dc16613fa70d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorsetstatus"></a>CDynamicAccessor::SetStatus
Задает состояние указанного столбца.  
  
## <a name="syntax"></a>Синтаксис  
  
```
bool SetStatus(DBORDINAL nColumn,   
   DBSTATUS status)throw();  

bool SetStatus(const CHAR* pColumnName,   
   DBSTATUS status) throw();  

bool SetStatus(const WCHAR* pColumnName,   
   DBSTATUS status) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nColumn`  
 [in] Номер столбца. Номера столбцов начинается с 1. Значение 0 ссылается на столбец закладки в том случае, если таковые имеются.  
  
 *status*  
 [in] Состояние столбца. В разделе [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в *Справочник программиста OLE DB* для получения дополнительной информации.  
  
 `pColumnName`  
 [in] Указатель на символьную строку, содержащую имя столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если успешно задано состояние указанного столбца. В противном случае эта функция возвращает **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)