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
ms.openlocfilehash: b86064c162dcacfbbc5877614c63d92d0f2bd347
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544534"
---
# <a name="transaction-object-interfaces"></a>Интерфейсы объекта транзакции

Объект Transaction определяет атомарную единицу работы в источнике данных и определяет, как эти единицы работы связаны друг с другом. Этот объект не поддерживается напрямую шаблонами поставщика OLE DB (то есть необходимо создать собственный объект).

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные OLE DB для объекта транзакции.

|Интерфейс|Обязательно?|Реализуется с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Обязательный|Нет|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Обязательный|Нет|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Необязательно|Нет|

## <a name="see-also"></a>См. также:

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
