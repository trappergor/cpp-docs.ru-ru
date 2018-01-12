---
title: "OLE DB Создание пулов ресурсов и служб | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5d3d9ddba2039c1b4445bdb8d4ee77e9a68d9796
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-db-resource-pooling-and-services"></a>Создание пулов ресурсов и служб OLE DB
Для работы с пулом, или любой службы OLE DB, поставщик должен поддерживать агрегирование всех объектов. Это требование OLE DB 1.5 или более поздней версии поставщика. Очень важно для службы. Поставщики, которые не поддерживают статистической обработки, невозможно создание пула и без дополнительных служб.  
  
 В составе пула, поставщики должны поддерживать модели свободных потоков. Пул ресурсов определяет модель согласно **DBPROP_THREADMODEL** свойство.  
  
 Если поставщик глобальное состояние может измениться, когда источник данных находится в инициализированном состоянии, он должен поддерживать новый **DBPROP_RESETDATASOURCE** свойство. Это свойство называется перед соединение используется повторно и дает возможность очистить состояние перед его повторным использованием поставщика. Если поставщик не может очистить какое-либо состояние, связанный с подключением, она может возвращать **DBPROPSTATUS_NOTSETTABLE** для свойства и соединение не будет использоваться повторно.  
  
 Поставщики, подключения к удаленной базе данных и может определить, будет ли поддерживать подключение может быть утеряно **DBPROP_CONNECTIONSTATUS** свойство. Это свойство позволяет службы OLE DB обнаруживать неработающие подключения и убедитесь, что они не возвращаются в пул.  
  
 Наконец автоматическое прикрепление транзакций обычно не работает, если она реализована на том же уровне, пулов. Поставщиков, которые поддерживают автоматическое прикрепление транзакций сами должны поддерживать отключение путем предоставления доступа к этим зачислением **DBPROP_INIT_OLEDBSERVICES, установить** свойство и отключение прикрепление, если **DBPROPVAL_OS_ TXNENLISTMENT** отменен.  
  
## <a name="see-also"></a>См. также  
 [Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)