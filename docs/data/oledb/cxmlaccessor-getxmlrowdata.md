---
title: "CXMLAccessor::GetXMLRowData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs:
- C++
helpviewer_keywords:
- GetXMLRowData method
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b4b0307b649b702ad78ddb90d9985e14df2331b1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cxmlaccessorgetxmlrowdata"></a>CXMLAccessor::GetXMLRowData
Получает все содержимое таблицы по строкам данных строка в формате XML.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,   
   bool bAppend = false) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `strOutput`  
 [out] Ссылка на буфер, содержащий данные таблицы должны быть получены. Данные форматируются как строковые данные с XML имена тегов, которые совпадают с именами столбцов в хранилище данных.  
  
 *bAppend*  
 [in] Логическое значение, указывающее, следует ли добавить строку в конец выходных данных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 Ниже показан способ форматирования данных в строке в формате XML. `DATA` ниже представляет строки данных. С помощью move методы для перемещения требуемой строки.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)