---
title: Интерфейсы объекта сеанса | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8208a372989fac5fa7c7b0c13b83eb27a4d1444b
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571436"
---
# <a name="session-object-interfaces"></a>Интерфейсы объекта сеанса
В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта сеанса.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](/previous-versions/windows/desktop/ms709721\(v=vs.85\))|Обязательный|Да|  
|[IOpenRowset](/previous-versions/windows/desktop/ms716946\(v=vs.85\))|Обязательный|Да|  
|[ISessionProperties](/previous-versions/windows/desktop/ms713721\(v=vs.85\))|Обязательный|Да|  
|[IAlterIndex](/previous-versions/windows/desktop/ms714943\(v=vs.85\))|Optional|Нет|  
|[IAlterTable](/previous-versions/windows/desktop/ms719764\(v=vs.85\))|Optional|Нет|  
|[IBindResource](/previous-versions/windows/desktop/ms714936\(v=vs.85\))|Optional|Нет|  
|[ICreateRow](/previous-versions/windows/desktop/ms716832\(v=vs.85\))|Optional|Нет|  
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625\(v=vs.85\))|Optional|Да|  
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\))|Optional|Да|  
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593\(v=vs.85\))|Optional|Нет|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816\(v=vs.85\))|Optional|Да|  
|[ITableCreation](/previous-versions/windows/desktop/ms713639\(v=vs.85\))|Optional|Нет|  
|[ITableDefinition](/previous-versions/windows/desktop/ms714277\(v=vs.85\))|Optional|Нет|  
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947\(v=vs.85\))|Optional|Нет|  
|[ITransaction](/previous-versions/windows/desktop/ms723053\(v=vs.85\))|Optional|Нет|  
|[Интерфейс ITransactionJoin](/previous-versions/windows/desktop/ms718071\(v=vs.85\))|Optional|Нет|  
|[Интерфейс ITransactionLocal](/previous-versions/windows/desktop/ms714893\(v=vs.85\))|Optional|Нет|  
|[ITransactionObject](/previous-versions/windows/desktop/ms713659\(v=vs.85\))|Optional|Нет|  
  
 Объект сеанса создает объект набора строк. Если поставщик поддерживает команды, сеанс также создает объект command (`CCommand`, реализации OLE DB `TCommand`). Реализует объект команды `ICommand` интерфейс и использует `ICommand::Execute` метод для выполнения команд на наборе строк, как показано на рисунке ниже.  
  
 ![Концептуальная схема поставщика](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)