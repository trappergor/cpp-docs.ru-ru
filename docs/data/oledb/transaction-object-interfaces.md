---
title: Интерфейсы объекта транзакции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ba98cfa4a88b695995902bdaca5e4ae3f33e5198
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339758"
---
# <a name="transaction-object-interfaces"></a>Интерфейсы объекта транзакции
Объект транзакции определяет атомарной единицей работы над источником данных и определяет, каким образом эти единицы работы связаны друг с другом. Этот объект не поддерживается напрямую с помощью шаблонов поставщика OLE DB (то есть необходимо создать собственный объект).  
  
 В следующей таблице показаны обязательные и необязательные интерфейсы, определенные в OLE DB для объекта транзакции.  
  
|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Обязательный|Нет|  
|[ITransaction](https://msdn.microsoft.com/library/ms723053.aspx)|Обязательный|Нет|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|Нет|  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)