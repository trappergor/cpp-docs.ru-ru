---
title: "Интерфейсы объекта источника данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b15ff70c505496fa6375ef01091e0826ec08d98d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-object-interfaces"></a>Интерфейсы объекта источника данных
В следующей таблице показаны обязательные и необязательные интерфейсы, определенные для объекта источника данных OLE DB.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|Обязательный|Да|  
|`IDBInitialize`|Обязательный|Да|  
|`IDBProperties`|Обязательный|Да|  
|[IPersist](http://msdn.microsoft.com/library/windows/desktop/ms688695)|Обязательный|Да|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|Нет|  
|`IDBDataSourceAdmin`|Optional|Нет|  
|`IDBInfo`|Optional|Нет|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Optional|Нет|  
|`ISupportErrorInfo`|Optional|Нет|  
  
 Источник данных реализует объект `IDBProperties`, `IDBInitialize`, и `IDBCreateSession` интерфейсов с помощью наследования. Можно выбрать поддержку дополнительных функций путем наследования от одного из этих классов реализации. Если вы хотите поддерживать `IDBDataSourceAdmin` интерфейс, должен наследовать из `IDBDataSourceAdminImpl` класса.  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)