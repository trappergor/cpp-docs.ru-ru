---
title: Интерфейсы объекта Rowset | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e8a1a5f5256087a8869426489fe01250b16fc598
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340515"
---
# <a name="rowset-object-interfaces"></a>Интерфейсы объекта Rowset
Ниже приведены обязательные и необязательные интерфейсы, определенные в OLE DB для объекта набора строк.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/library/ms719672.aspx)|Обязательный|Да|  
|[IColumnsInfo](https://msdn.microsoft.com/library/ms724541.aspx)|Обязательный|Да|  
|[Интерфейс IConvertType](https://msdn.microsoft.com/library/ms715926.aspx)|Обязательный|Да|  
|[IRowset](https://msdn.microsoft.com/library/ms720986.aspx)|Обязательный|Да|  
|[IRowsetInfo](https://msdn.microsoft.com/library/ms724541.aspx)|Обязательный|Да|  
|[IChapteredRowset](https://msdn.microsoft.com/library/ms718180.aspx)|Optional|Нет|  
|[IColumnsInfo2](https://msdn.microsoft.com/library/ms712953.aspx)|Optional|Нет|  
|[IColumnsRowset](https://msdn.microsoft.com/library/ms722657.aspx)|Optional|Нет|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|Да (с помощью ATL)|  
|[IDBAsynchStatus](https://msdn.microsoft.com/library/ms709832.aspx)|Optional|Нет|  
|[IGetRow](https://msdn.microsoft.com/library/ms718047.aspx)|Optional|Нет|  
|[IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx)|Optional|Да|  
|[IRowsetChapterMember](https://msdn.microsoft.com/library/ms725430.aspx)|Optional|Нет|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/library/ms709700.aspx)|Optional|Нет|  
|[IRowsetFind](https://msdn.microsoft.com/library/ms724221.aspx)|Optional|Нет|  
|[IRowsetIdentity](https://msdn.microsoft.com/library/ms715913.aspx)|Необязательно (но требуемый для поставщиков уровня 0)|Да|  
|[IRowsetIndex](https://msdn.microsoft.com/library/ms719604.aspx)|Optional|Нет|  
|[IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx)|Optional|Да|  
|[IRowsetRefresh](https://msdn.microsoft.com/library/ms714892.aspx)|Optional|Нет|  
|[IRowsetScroll](https://msdn.microsoft.com/library/ms712984.aspx)|Optional|Нет|  
|[IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx)|Optional|Да|  
|[IRowsetView](https://msdn.microsoft.com/library/ms709755.aspx)|Optional|Нет|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|Да|  
|[IRowsetBookmark](https://msdn.microsoft.com/library/ms714246.aspx)|Optional|Нет|  
  
 Реализует объект набора строк, создаваемые мастером `IAccessor`, `IRowset`, и `IRowsetInfo` через наследование. `IAccessorImpl` Привязывает обоих выходных столбцов. `IRowset` Интерфейс обработки выборок строк и данных. `IRowsetInfo` Интерфейс обрабатывает свойства набора строк.  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)