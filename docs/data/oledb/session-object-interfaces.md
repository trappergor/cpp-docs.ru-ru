---
title: Интерфейсы объекта сеанса
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: 7e8a9cd204a07afc2b14c6a1e31e7c970c27cfc2
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423382"
---
# <a name="session-object-interfaces"></a>Интерфейсы объекта сеанса

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта сеанса.

|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|Обязательный|Да|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|Обязательный|Да|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|Обязательный|Да|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943(v=vs.85))|Optional|Нет|
|[IAlterTable](/previous-versions/windows/desktop/ms719764(v=vs.85))|Optional|Нет|
|[IBindResource](/previous-versions/windows/desktop/ms714936(v=vs.85))|Optional|Нет|
|[ICreateRow](/previous-versions/windows/desktop/ms716832(v=vs.85))|Optional|Нет|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|Optional|Да|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|Optional|Да|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|Optional|Нет|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|Да|
|[ITableCreation](/previous-versions/windows/desktop/ms713639(v=vs.85))|Optional|Нет|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|Optional|Нет|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947(v=vs.85))|Optional|Нет|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Optional|Нет|
|[Интерфейс ITransactionJoin](/previous-versions/windows/desktop/ms718071(v=vs.85))|Optional|Нет|
|[Интерфейс ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|Optional|Нет|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659(v=vs.85))|Optional|Нет|

Объект сеанса создает объект набора строк. Если поставщик поддерживает команды, сеанс также создает объект command (`CCommand`, реализации OLE DB `TCommand`). Реализует объект команды `ICommand` интерфейс и использует `ICommand::Execute` метод для выполнения команд на наборе строк, как показано на рисунке ниже.

![Концептуальная схема поставщика](../../data/oledb/media/vc4u551.gif "концептуальная схема поставщика")

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
