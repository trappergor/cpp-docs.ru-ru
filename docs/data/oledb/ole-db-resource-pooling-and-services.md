---
title: OLE DB Создание пулов ресурсов и служб | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3cf18d1b06c6a738659bf30bf58fc10c48aa0ce5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091040"
---
# <a name="ole-db-resource-pooling-and-services"></a>Создание пулов ресурсов и служб OLE DB

Для работы с пулами OLE DB или с любой службой OLE DB, поставщик должен поддерживать агрегирование всех объектов. Это обязательное требование OLE DB 1.5 или более поздней версии поставщика. Крайне важно для удобного служб. Поставщики, которые не поддерживают агрегирование не может быть помещен в пул и без дополнительных служб.  
  
В пул, поставщики должны поддерживать модели свободных потоков. Пул ресурсов определяет модель согласно `DBPROP_THREADMODEL` свойство.  
  
Если поставщик глобальное состояние может измениться, когда источник данных находится в инициализированном состоянии, он должен поддерживать новый `DBPROP_RESETDATASOURCE` свойство. Это свойство вызывается прежде, чем соединение используется повторно и предоставляет возможность очистки состояния перед его повторным использованием поставщика. Если поставщик не может очистить связанный с соединением, он может возвращать `DBPROPSTATUS_NOTSETTABLE` для свойства и подключение не будет использоваться повторно.  
  
Поставщики, которые подключаются к удаленной базе данных и может обнаружить, что подключения могут быть потеряны, должен ли поддерживать `DBPROP_CONNECTIONSTATUS` свойство. Это свойство позволяет службы OLE DB для обнаружения мертвых соединений и убедитесь, что они не возвращаются в пул.  
  
Наконец автоматическое прикрепление транзакций обычно не работать, если он реализован на том же уровне, пулов. Поставщики, которые поддерживают автоматическое прикрепление транзакций сами должны поддерживать отключение этим зачислением, предоставляя `DBPROP_INIT_OLEDBSERVICES` свойство и отключение прикрепления, если `DBPROPVAL_OS_TXNENLISTMENT` отменен.  
  
## <a name="see-also"></a>См. также  

[Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)