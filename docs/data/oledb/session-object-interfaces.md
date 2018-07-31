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
ms.openlocfilehash: 01d08fb35a1e954aad07153f63ad3ed34282570d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337850"
---
# <a name="session-object-interfaces"></a>Интерфейсы объекта сеанса
В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта сеанса.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx)|Обязательный|Да|  
|[IOpenRowset](https://msdn.microsoft.com/library/ms716946.aspx)|Обязательный|Да|  
|[ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx)|Обязательный|Да|  
|[IAlterIndex](https://msdn.microsoft.com/library/ms714943.aspx)|Optional|Нет|  
|[IAlterTable](https://msdn.microsoft.com/library/ms719764.aspx)|Optional|Нет|  
|[IBindResource](https://msdn.microsoft.com/library/ms714936.aspx)|Optional|Нет|  
|[ICreateRow](https://msdn.microsoft.com/library/ms716832.aspx)|Optional|Нет|  
|[IDBCreateCommand](https://msdn.microsoft.com/library/ms711625.aspx)|Optional|Да|  
|[IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)|Optional|Да|  
|[IIndexDefinition](https://msdn.microsoft.com/library/ms711593.aspx)|Optional|Нет|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|Да|  
|[ITableCreation](https://msdn.microsoft.com/library/ms713639.aspx)|Optional|Нет|  
|[ITableDefinition](https://msdn.microsoft.com/library/ms714277.aspx)|Optional|Нет|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/library/ms720947.aspx)|Optional|Нет|  
|[ITransaction](https://msdn.microsoft.com/library/ms723053.aspx)|Optional|Нет|  
|[Интерфейс ITransactionJoin](https://msdn.microsoft.com/library/ms718071.aspx)|Optional|Нет|  
|[Интерфейс ITransactionLocal](https://msdn.microsoft.com/library/ms714893.aspx)|Optional|Нет|  
|[ITransactionObject](https://msdn.microsoft.com/library/ms713659.aspx)|Optional|Нет|  
  
 Объект сеанса создает объект набора строк. Если поставщик поддерживает команды, сеанс также создает объект command (`CCommand`, реализации OLE DB `TCommand`). Реализует объект команды `ICommand` интерфейс и использует `ICommand::Execute` метод для выполнения команд на наборе строк, как показано на рисунке ниже.  
  
 ![Концептуальная схема поставщика](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)