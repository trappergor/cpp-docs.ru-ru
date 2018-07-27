---
title: Интерфейсы объекта сеанса | Документы Microsoft
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
ms.openlocfilehash: f591e62874bd6924dd60077b921bbfc67600af1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112931"
---
# <a name="session-object-interfaces"></a>Интерфейсы объекта сеанса
В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта сеанса.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx)|Обязательно|Да|  
|[IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx)|Обязательно|Да|  
|[ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx)|Обязательно|Да|  
|[IAlterIndex](https://msdn.microsoft.com/en-us/library/ms714943.aspx)|Необязательный|Нет|  
|[IAlterTable](https://msdn.microsoft.com/en-us/library/ms719764.aspx)|Необязательный|Нет|  
|[IBindResource](https://msdn.microsoft.com/en-us/library/ms714936.aspx)|Необязательный|Нет|  
|[ICreateRow](https://msdn.microsoft.com/en-us/library/ms716832.aspx)|Необязательный|Нет|  
|[IDBCreateCommand](https://msdn.microsoft.com/en-us/library/ms711625.aspx)|Необязательный|Да|  
|[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)|Необязательный|Да|  
|[IIndexDefinition](https://msdn.microsoft.com/en-us/library/ms711593.aspx)|Необязательный|Нет|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Необязательный|Да|  
|[ITableCreation](https://msdn.microsoft.com/en-us/library/ms713639.aspx)|Необязательный|Нет|  
|[ITableDefinition](https://msdn.microsoft.com/en-us/library/ms714277.aspx)|Необязательный|Нет|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/en-us/library/ms720947.aspx)|Необязательный|Нет|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Необязательный|Нет|  
|[Интерфейс ITransactionJoin](https://msdn.microsoft.com/en-us/library/ms718071.aspx)|Необязательный|Нет|  
|[Интерфейс ITransactionLocal](https://msdn.microsoft.com/en-us/library/ms714893.aspx)|Необязательный|Нет|  
|[ITransactionObject](https://msdn.microsoft.com/en-us/library/ms713659.aspx)|Необязательный|Нет|  
  
 Объект сеанса создает объект набора строк. Если поставщик поддерживает команды, сеанс также создает командный объект (`CCommand`, реализации OLE DB **TCommand**). Реализует объект команды `ICommand` интерфейс и использует `ICommand::Execute` метод для выполнения команд на наборе строк, как показано на следующем рисунке.  
  
 ![Концептуальная схема поставщика](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)