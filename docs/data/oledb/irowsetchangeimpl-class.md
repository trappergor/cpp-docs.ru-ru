---
title: "Класс IRowsetChangeImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
dev_langs: C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4dc31fc66f28f6fd9a8d9e9bc7122bf2aa7b2b73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetchangeimpl-class"></a>Класс IRowsetChangeImpl
Реализация шаблонов OLE DB [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) интерфейса в спецификации OLE DB.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >   
>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetChangeImpl`.  
  
 `Storage`  
 Записи пользователя.  
  
 `BaseInterface`  
 Базовый класс для интерфейса, такие как `IRowsetChange`.  
  
 `RowClass`  
 Устройство хранения для дескриптора строки.  
  
 `MapClass`  
 Устройство хранения для все дескрипторы строк, удерживаемые поставщика.  
  
## <a name="members"></a>Члены  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|Удаляет строки из набора строк.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|Вставляет строку в наборе строк.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|Задает значения данных в одном или нескольких столбцах.|  
  
### <a name="implementation-method-callback"></a>Реализация метода (обратный вызов)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|Overidden поставщиком для фиксации данных к своему хранилищу.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс не отвечает за операции записи непосредственно в хранилище данных. «Immediate» означает, когда конечный пользователь (лицом, использующим потребитель) делает все изменения, эти изменения немедленно переносятся данные хранения (и не может быть отменено).  
  
 `IRowsetChangeImpl`реализует OLE DB `IRowsetChange` интерфейс, позволяющий обновления значений столбцов в существующих строках, удаление строк и вставки новых строк.  
  
 Реализация шаблонов OLE DB поддерживает все базовые методы (`SetData`, `InsertRow`, и `DeleteRows`).  
  
> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде ЧЕМ пытаться реализации поставщика:  
  
-   [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Глава 6 *справочника программиста OLE DB*  
  
-   См. также как `RUpdateRowset` класс используется в разделе Создание  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)