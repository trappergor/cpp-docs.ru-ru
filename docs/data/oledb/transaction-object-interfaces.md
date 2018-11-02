---
title: Интерфейсы объекта транзакции
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
ms.openlocfilehash: af67edca97cbfd644668ed48b3145cdbc38636a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564324"
---
# <a name="transaction-object-interfaces"></a>Интерфейсы объекта транзакции

Объект транзакции определяет атомарной единицей работы над источником данных и определяет, каким образом эти единицы работы связаны друг с другом. Этот объект не поддерживается напрямую с помощью шаблонов поставщика OLE DB (то есть необходимо создать собственный объект).

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта транзакции.

|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Обязательный|Нет|
|[ITransaction](/previous-versions/windows/desktop/ms723053)|Обязательный|Нет|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|Нет|

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
