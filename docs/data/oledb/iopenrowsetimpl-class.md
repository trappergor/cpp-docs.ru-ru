---
title: Класс IOpenRowsetImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dd34987fcff3bee663a06276e3ded3c44d7ae77c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102089"
---
# <a name="iopenrowsetimpl-class"></a>Класс IOpenRowsetImpl
Предоставляет реализацию для `IOpenRowset` интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>Параметры  
 `SessionClass`  
 Класс, производный от `IOpenRowsetImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Создает объект набора строк. Не вызывается непосредственно пользователем.|  
|[Функции OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса. (Не в ATLDB. H)|  
  
## <a name="remarks"></a>Примечания  
 [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) интерфейса является обязательным для объекта сеанса. Он открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)