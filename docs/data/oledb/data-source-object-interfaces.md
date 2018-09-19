---
title: Интерфейсы объекта источника данных | Документация Майкрософт
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
ms.openlocfilehash: e1e64d5f41950492c3c7076160e6d134f7eb62cf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099655"
---
# <a name="data-source-object-interfaces"></a>Интерфейсы объекта источника данных

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные для объекта источника данных OLE DB.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|Обязательный|Да|  
|`IDBInitialize`|Обязательный|Да|  
|`IDBProperties`|Обязательный|Да|  
|[IPersist](/windows/desktop/api/objidl/nn-objidl-ipersist)|Обязательный|Да|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|Нет|  
|`IDBDataSourceAdmin`|Optional|Нет|  
|`IDBInfo`|Optional|Нет|  
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Optional|Нет|  
|`ISupportErrorInfo`|Optional|Нет|  
  
Источник данных реализует объект `IDBProperties`, `IDBInitialize`, и `IDBCreateSession` интерфейсы через наследование. Вы можете поддерживать дополнительные функциональные возможности путем наследования от одного из этих классов реализации. Если вы хотите поддерживать `IDBDataSourceAdmin` интерфейс, необходимо наследовать от `IDBDataSourceAdminImpl` класса.  
  
## <a name="see-also"></a>См. также  

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)