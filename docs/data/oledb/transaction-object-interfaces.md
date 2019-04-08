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
ms.openlocfilehash: 0caecc797a3175d5769f98e181e1d99ef6b1ad16
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034038"
---
# <a name="transaction-object-interfaces"></a>Интерфейсы объекта транзакции

Объект транзакции определяет атомарной единицей работы над источником данных и определяет, каким образом эти единицы работы связаны друг с другом. Этот объект не поддерживается напрямую с помощью шаблонов поставщика OLE DB (то есть необходимо создать собственный объект).

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта транзакции.

|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Обязательный|Нет|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Обязательный|Нет|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|Нет|

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
