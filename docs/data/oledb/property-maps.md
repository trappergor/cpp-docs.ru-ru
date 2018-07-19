---
title: Сопоставления свойств | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d7664562ff31f1f5871fab4ce74c1652370a540d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103220"
---
# <a name="property-maps"></a>Сопоставления свойств
Помимо сеансов, набор строк и дополнительных объектов команды каждый поставщик поддерживает одно или несколько свойств. Эти свойства определяются в сопоставлениях свойств, содержащихся в файлах заголовков, созданные мастером поставщика OLE DB. Каждый файл заголовка содержит сопоставление для свойств в группе свойств OLE DB, определенных для объекта или объектов, определенных в этом файле. Файл заголовка, который содержит объект источника данных также содержится в схеме сопоставления свойств для [свойств DataSource](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx). Session.h содержится в схеме сопоставления свойств для [свойства сеанса](https://msdn.microsoft.com/en-us/library/ms714221.aspx). Объекты наборов строк и команд, находятся в одном файле заголовка, вызывается *projectname*RS.h. Эти свойства являются членами [свойства набора строк](https://msdn.microsoft.com/en-us/library/ms711252.aspx) группы.  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)