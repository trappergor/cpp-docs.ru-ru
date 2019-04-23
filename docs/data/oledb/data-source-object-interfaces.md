---
title: Интерфейсы объекта источника данных
ms.date: 10/24/2018
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
ms.openlocfilehash: fc8d2f5edf854766dcb5dcc8ed6d57a849b8f2a0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033194"
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

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
