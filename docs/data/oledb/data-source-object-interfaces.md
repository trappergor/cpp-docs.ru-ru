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
ms.openlocfilehash: a615694a9db75cdaf3b187cf6d29248bd26ef978
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544606"
---
# <a name="data-source-object-interfaces"></a>Интерфейсы объекта источника данных

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные OLE DB для объекта источника данных.

|Интерфейс|Обязательно?|Реализуется с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|Обязательный|Да|
|`IDBInitialize`|Обязательный|Да|
|`IDBProperties`|Обязательный|Да|
|[IPersist](/windows/win32/api/objidl/nn-objidl-ipersist)|Обязательный|Да|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Необязательно|Нет|
|`IDBDataSourceAdmin`|Необязательно|Нет|
|`IDBInfo`|Необязательно|Нет|
|[IPersistFile](/windows/win32/api/objidl/nn-objidl-ipersistfile)|Необязательно|Нет|
|`ISupportErrorInfo`|Необязательно|Нет|

Объект источника данных реализует интерфейсы `IDBProperties`, `IDBInitialize`и `IDBCreateSession` посредством наследования. Можно выбрать поддержку дополнительных функций путем наследования или наследования от одного из этих классов реализации. Если требуется поддержка интерфейса `IDBDataSourceAdmin`, необходимо наследовать от класса `IDBDataSourceAdminImpl`.

## <a name="see-also"></a>См. также:

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
