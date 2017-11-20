---
title: "Класс IRowsetUpdateImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
dev_langs: C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fe93031417b8fc7717be13007b0fcfc5d08a2c40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetupdateimpl-class"></a>Класс IRowsetUpdateImpl
Реализация шаблонов OLE DB [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  
class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass  
>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetUpdateImpl`.  
  
 `Storage`  
 Записи пользователя.  
  
 `UpdateArray`  
 Массив, содержащий кэшированные данные для обновления набора строк.  
  
 `RowClass`  
 Устройство хранения для **HROW**.  
  
 `MapClass`  
 Устройство хранения для все дескрипторы строк, удерживаемые поставщика.  
  
## <a name="members"></a>Члены  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)  
  
|||  
|-|-|  
|[SetData](../../data/oledb/irowsetupdateimpl-setdata.md)|Задает значения данных в одном или нескольких столбцах.|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>Методы интерфейса (используется с IRowsetUpdate)  
  
|||  
|-|-|  
|[GetOriginalData](../../data/oledb/irowsetupdateimpl-getoriginaldata.md)|Возвращает данные последней передачи или получена из источника данных, без учета ожидающих изменений.|  
|[GetPendingRows](../../data/oledb/irowsetupdateimpl-getpendingrows.md)|Возвращает список строк с отложенными изменениями.|  
|[GetRowStatus](../../data/oledb/irowsetupdateimpl-getrowstatus.md)|Возвращает состояние указанной строки.|  
|[Отменить](../../data/oledb/irowsetupdateimpl-undo.md)|Отменяет все изменения в строку с момента последней выборки или обновления.|  
|[Обновление](../../data/oledb/irowsetupdateimpl-update.md)|Передает любые изменения, внесенные в строку с момента последней выборки или обновления.|  
  
### <a name="implementation-methods-callback"></a>Реализация методов (обратный вызов)  
  
|||  
|-|-|  
|[IsUpdateAllowed](../../data/oledb/irowsetupdateimpl-isupdateallowed.md)|Используется для проверки для обеспечения целостности данных, безопасности и т. д рассматриваемого обновления.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_mapCachedData](../../data/oledb/irowsetupdateimpl-m-mapcacheddata.md)|Содержит исходные данные для отложенной операции.|  
  
## <a name="remarks"></a>Примечания  
 Сначала необходимо прочесть и понять, в документации по [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx), так как все описанное существует также применяется здесь. Также следует ознакомиться с главе 6 *Справочник программиста OLE DB* о задании данных.  
  
 `IRowsetUpdateImpl`реализует OLE DB `IRowsetUpdate` интерфейс, который позволяет потребителям приостановить передачу изменений, внесенных с `IRowsetChange` для источника данных и отменить изменения перед их отправкой.  
  
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
 [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)