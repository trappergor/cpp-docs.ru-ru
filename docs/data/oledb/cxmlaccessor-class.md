---
title: Класс CXMLAccessor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 916e9dbe4e142192e4e716f57f97d5bd6865c709
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102912"
---
# <a name="cxmlaccessor-class"></a>Класс CXMLAccessor
Позволяет доступ к источникам данных как строковые данные, когда схема хранилища данных (базовая структура).  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|Извлекает сведения о столбце.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|Извлекает все содержимое таблицы по строкам.|  
  
## <a name="remarks"></a>Примечания  
 Тем не менее `CXMLAccessor` отличается от `CDynamicStringAccessorW` в том, что он преобразует все данные из хранилища данных в виде XML-данных (с тегом). Это особенно полезно для выхода на веб-страницы, использующие XML. Имена тегов XML будет как можно точнее соответствовать имена столбцов в хранилище данных.  
  
 Используйте `CDynamicAccessor` методов, чтобы получить сведения о столбцах. Используйте эти сведения для столбца для динамического создания метода доступа во время выполнения.  
  
 Сведения о столбце хранится в буфере, созданном и управляемым данным классом. Получить сведения о столбце с помощью [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) или получить данные столбцов, строк с помощью [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md).  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-класс](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)   
 [Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)   
 [Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)