---
title: "CDynamicAccessor::GetValue | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- GetValue method
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b572faceb1ea27f05bb1a422a86de4b42f9175c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorgetvalue"></a>CDynamicAccessor::GetValue
Извлекает данные для указанного столбца.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
void* GetValue(DBORDINAL nColumn) const throw();  

void* GetValue(const CHAR* pColumnName) const throw();  

void* GetValue(const WCHAR* pColumnName) const throw();  

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `ctype`  
 [in] Шаблонный параметр, который обрабатывает любого типа данных, за исключением строковых типов (**CHAR\***, **WCHAR\***), который требуют специальной обработки. `GetValue` использует соответствующий тип данных зависимости от того, что указано здесь.  
  
 `nColumn`  
 [in] Номер столбца. Номера столбцов начинается с 1. Значение 0 ссылается на столбец закладки в том случае, если таковые имеются.  
  
 `pColumnName`  
 [in] Имя столбца.  
  
 `pData`  
 [out] Указатель на содержимое указанного столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если требуется передать строковые данные, используйте нешаблонной версии `GetValue`. Версии нешаблонной этот метод возвращает **void\***, который указывает на часть буфер, содержащий данные указанного столбца. Возвращает **NULL** Если столбец не найден.  
  
 Для всех других типов данных, проще использовать шаблонные версии `GetValue`. Шаблонные версии возвращают **true** в случае успешного выполнения или **false** при сбое.  
  
## <a name="remarks"></a>Примечания  
 С помощью версии нешаблонной возвращать столбцы, содержащие строки и шаблонные версии для столбцов, содержащих другие типы данных.  
  
 В режиме отладки, будет работать утверждение, если размер `pData` не равно размер столбца, на который он указывает.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)