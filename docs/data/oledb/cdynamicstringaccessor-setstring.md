---
title: "CDynamicStringAccessor::SetString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 43956a0bb9ce673e96c4a8c06194a6ef48a56495
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicstringaccessorsetstring"></a>CDynamicStringAccessor::SetString
Задает данные указанного столбца в виде строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT SetString(DBORDINAL nColumn,  
  BaseType* data) throw();  


HRESULT SetString(const CHAR* pColumnName,  
   BaseType* data) throw();  


HRESULT SetString(const WCHAR* pColumnName,  
   BaseType* data) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nColumn`  
 [in] Номер столбца. Номера столбцов начинается с 1. Специальное значение 0 ссылается на столбец закладки в том случае, если таковые имеются.  
  
 `pColumnName`  
 [in] Указатель на строку символов, которая содержит имя столбца.  
  
 `data`  
 [in] Указатель на данные строки для записи к указанному столбцу.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на строковое значение, для которого требуется задать указанного столбца. Значение имеет тип `BaseType`, которое будет `CHAR` или `WCHAR` в зависимости от того, следует ли `_UNICODE` или не определено.  
  
## <a name="remarks"></a>Примечания  
 Второй переопределение принимает форму именем столбца как строки ANSI и третий переопределения формы принимает имя столбца в виде строки в Юникоде.  
  
 Если `_SECURE_ATL` определяется должен иметь ненулевое значение, сбой утверждения среды выполнения создается, если входные данные `data` строки превышает максимально допустимую длину столбца данных, на которую указывает ссылка. В противном случае входная строка будет усечено, если он превышает максимально допустимую длину.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)