---
title: "Сопоставления свойств | Документы Microsoft"
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
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 020479236bd86659ee4df783bf2056613cfac753
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="property-maps"></a>Сопоставления свойств
Помимо сеансов, набор строк и дополнительных объектов команды каждый поставщик поддерживает одно или несколько свойств. Эти свойства определяются в сопоставлениях свойств, содержащихся в файлах заголовков, созданные мастером поставщика OLE DB. Каждый файл заголовка содержит сопоставление для свойств в группе свойств OLE DB, определенных для объекта или объектов, определенных в этом файле. Файл заголовка, который содержит объект источника данных также содержится в схеме сопоставления свойств для [свойств DataSource](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx). Session.h содержится в схеме сопоставления свойств для [свойства сеанса](https://msdn.microsoft.com/en-us/library/ms714221.aspx). Объекты наборов строк и команд, находятся в одном файле заголовка, вызывается *projectname*RS.h. Эти свойства являются членами [свойства набора строк](https://msdn.microsoft.com/en-us/library/ms711252.aspx) группы.  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)