---
title: Интерфейсы объекта источника данных | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c8aaed0a9f50e20dba5938b9b37425f4caa2bb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101881"
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