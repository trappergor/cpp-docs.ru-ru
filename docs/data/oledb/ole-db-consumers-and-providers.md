---
title: "Получатели и поставщики | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec0a8764ef8f5e906ad399d76a5a004c313f500b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-consumers-and-providers"></a>Получатели и поставщики OLE DB
В архитектуре OLE DB используется модель получателей и поставщиков. Получатель выполняет запросы к данным. Поставщик отвечает на эти запросы, размещает данные в табличном формате и возвращает их потребителю. Любой вызов, объекта-получателя должен быть реализован в поставщике.  
  
 С технической точки зрения, потребитель — это любой системе или приложении код (не обязательно компонент OLE DB) для доступа к данным через интерфейсы OLE DB. Интерфейсы реализованы в поставщике. Таким образом поставщик — любой программный компонент, реализующий интерфейсы OLE DB для инкапсуляции доступа к данным и предоставлять его в другие объекты (то есть, получателям).  
  
 С точки зрения ролей потребитель вызывает методы в интерфейсах OLE DB; Поставщик OLE DB реализует необходимые интерфейсы OLE DB.  
  
 OLE DB позволяет избежать условия клиентом и сервером, так как эти роли не всегда имеют смысла, особенно в случае n уровневые. Поскольку объект-получатель может быть компонентом на уровне, обслуживающем другой компонент, будет вызывать его, клиент может вызвать путаницу. Кроме того поставщик иногда выступает более драйвер базы данных, чем на сервере.  
  
## <a name="see-also"></a>См. также  
 [Программирование объектов OLE DB](../../data/oledb/ole-db-programming.md)   
 [Общие сведения о программировании OLE DB](../../data/oledb/ole-db-programming-overview.md)