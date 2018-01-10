---
title: "Интерфейсы объекта сеанса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: abb869becff4f2a4af9d489736c21b66674cc112
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="session-object-interfaces"></a>Интерфейсы объекта сеанса
В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта сеанса.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx)|Обязательный|Да|  
|[IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx)|Обязательный|Да|  
|[ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx)|Обязательный|Да|  
|[IAlterIndex](https://msdn.microsoft.com/en-us/library/ms714943.aspx)|Optional|Нет|  
|[IAlterTable](https://msdn.microsoft.com/en-us/library/ms719764.aspx)|Optional|Нет|  
|[IBindResource](https://msdn.microsoft.com/en-us/library/ms714936.aspx)|Optional|Нет|  
|[ICreateRow](https://msdn.microsoft.com/en-us/library/ms716832.aspx)|Optional|Нет|  
|[IDBCreateCommand](https://msdn.microsoft.com/en-us/library/ms711625.aspx)|Optional|Да|  
|[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)|Optional|Да|  
|[IIndexDefinition](https://msdn.microsoft.com/en-us/library/ms711593.aspx)|Optional|Нет|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|Да|  
|[ITableCreation](https://msdn.microsoft.com/en-us/library/ms713639.aspx)|Optional|Нет|  
|[ITableDefinition](https://msdn.microsoft.com/en-us/library/ms714277.aspx)|Optional|Нет|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/en-us/library/ms720947.aspx)|Optional|Нет|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Optional|Нет|  
|[Интерфейс ITransactionJoin](https://msdn.microsoft.com/en-us/library/ms718071.aspx)|Optional|Нет|  
|[Интерфейс ITransactionLocal](https://msdn.microsoft.com/en-us/library/ms714893.aspx)|Optional|Нет|  
|[ITransactionObject](https://msdn.microsoft.com/en-us/library/ms713659.aspx)|Optional|Нет|  
  
 Объект сеанса создает объект набора строк. Если поставщик поддерживает команды, сеанс также создает командный объект (`CCommand`, реализации OLE DB **TCommand**). Реализует объект команды `ICommand` интерфейс и использует `ICommand::Execute` метод для выполнения команд на наборе строк, как показано на следующем рисунке.  
  
 ![Концептуальная схема поставщика](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)