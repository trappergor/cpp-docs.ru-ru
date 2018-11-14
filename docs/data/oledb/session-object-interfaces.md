---
title: Интерфейсы объекта сеанса
ms.date: 10/24/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: 6b4748b804572c72b75f63b8ea2473818bdac989
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556625"
---
# <a name="session-object-interfaces"></a>Интерфейсы объекта сеанса

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта сеанса.

|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](https://docs.microsoft.com/previous-versions/windows/desktop/ms709721(v=vs.85))|Обязательный|Да|
|[IOpenRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms716946(v=vs.85))|Обязательный|Да|
|[ISessionProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms713721(v=vs.85))|Обязательный|Да|
|[IAlterIndex](https://docs.microsoft.com/previous-versions/windows/desktop/ms714943(v=vs.85))|Optional|Нет|
|[IAlterTable](https://docs.microsoft.com/previous-versions/windows/desktop/ms719764(v=vs.85))|Optional|Нет|
|[IBindResource](https://docs.microsoft.com/previous-versions/windows/desktop/ms714936(v=vs.85))|Optional|Нет|
|[ICreateRow](https://docs.microsoft.com/previous-versions/windows/desktop/ms716832(v=vs.85))|Optional|Нет|
|[IDBCreateCommand](https://docs.microsoft.com/previous-versions/windows/desktop/ms711625(v=vs.85))|Optional|Да|
|[IDBSchemaRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms713686(v=vs.85))|Optional|Да|
|[IIndexDefinition](https://docs.microsoft.com/previous-versions/windows/desktop/ms711593(v=vs.85))|Optional|Нет|
|[ISupportErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|Да|
|[ITableCreation](https://docs.microsoft.com/previous-versions/windows/desktop/ms713639(v=vs.85))|Optional|Нет|
|[ITableDefinition](https://docs.microsoft.com/previous-versions/windows/desktop/ms714277(v=vs.85))|Optional|Нет|
|[ITableDefinitionWithConstraints](https://docs.microsoft.com/previous-versions/windows/desktop/ms720947(v=vs.85))|Optional|Нет|
|[ITransaction](https://docs.microsoft.com/previous-versions/windows/desktop/ms723053(v=vs.85))|Optional|Нет|
|[Интерфейс ITransactionJoin](https://docs.microsoft.com/previous-versions/windows/desktop/ms718071(v=vs.85))|Optional|Нет|
|[Интерфейс ITransactionLocal](https://docs.microsoft.com/previous-versions/windows/desktop/ms714893(v=vs.85))|Optional|Нет|
|[ITransactionObject](https://docs.microsoft.com/previous-versions/windows/desktop/ms713659(v=vs.85))|Optional|Нет|

Объект сеанса создает объект набора строк. Если поставщик поддерживает команды, сеанс также создает объект command (`CCommand`, реализации OLE DB `TCommand`). Реализует объект команды `ICommand` интерфейс и использует `ICommand::Execute` метод для выполнения команд на наборе строк, как показано на рисунке ниже.

![Концептуальная схема поставщика](../../data/oledb/media/vc4u551.gif "vc4u551")

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
