---
title: CXMLAccessor::GetXMLColumnData | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
dev_langs:
- C++
helpviewer_keywords:
- GetXMLColumnData method
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ad3921a25e01f3269fe50f37fbc227a60e12cb43
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100659"
---
# <a name="cxmlaccessorgetxmlcolumndata"></a>CXMLAccessor::GetXMLColumnData
Получает тип сведения о столбцах таблицы в виде строки в формате XML по столбцу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `strOutput`  
 [out] Ссылка на строковый буфер, содержащий сведения о типе столбца требуется получить. Строка дополняется имена тегов XML, которые совпадают с именами столбцов в хранилище данных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 Ниже показано, как сведения о типе столбца форматируется в формате XML. `type` Указывает тип данных столбца. Обратите внимание, что типы данных основаны на типах данных OLE DB, не те базы данных, к которому выполняется доступ.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)