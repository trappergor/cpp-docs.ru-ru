---
title: Класс CDBPropSet | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d75715ed0dc65fbbf5b581bfea48816e5bd00ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdbpropset-class"></a>Класс CDBPropSet
Наследует от **DBPROPSET** структуры и добавляет конструктор, который инициализирует ключевых полей и `AddProperty` доступа к методу.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[addProperty](../../data/oledb/cdbpropset-addproperty.md)|Добавляет свойство в наборе свойств.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|Конструктор.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Наборы **guidPropertySet** поле **DBPROPSET** структуры.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](../../data/oledb/cdbpropset-operator-equal.md)|Назначает содержимое для одного свойства.|  
  
## <a name="remarks"></a>Примечания  
 Использование поставщиков и потребителей OLE DB **DBPROPSET** структур для передачи массивов `DBPROP` структуры. Каждый `DBPROP` структура представляет одно свойство, которое может быть установлено.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Cdbpropidset-класс](../../data/oledb/cdbpropidset-class.md)   
 [Структура DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [Структуры DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)