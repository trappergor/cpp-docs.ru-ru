---
title: CDynamicStringAccessor::GetString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
dev_langs:
- C++
helpviewer_keywords:
- GetString method
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc23fe73eb0d804d0b53950885b1b83aba58ff91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicstringaccessorgetstring"></a>CDynamicStringAccessor::GetString
Возвращает данные указанного столбца как строка.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      BaseType* GetString(DBORDINAL nColumn) const throw();  

BaseType* GetString(const CHAR* pColumnName) const throw();  

BaseType* GetString(const WCHAR* pColumnName) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nColumn`  
 [in] Номер столбца. Номера столбцов начинается с 1. Значение 0 ссылается на столбец закладки в том случае, если таковые имеются.  
  
 `pColumnName`  
 [in] Указатель на строку символов, которая содержит имя столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на строковое значение, полученных из указанного столбца. Значение имеет тип ***BaseType***, который может быть **CHAR** или **WCHAR** в зависимости от того, определен ли _UNICODE. Возвращает значение NULL, если указанный столбец не найден.  
  
## <a name="remarks"></a>Примечания  
 Второй, переопределяют принимает форму имени столбца в строку ANSI. Третий переопределение принимает форму имени столбца как строка Юникода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)