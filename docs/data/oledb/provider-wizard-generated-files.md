---
title: "Созданные мастером поставщика файлы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27fb95e5dc1c417d3dfb03217463a8ef683f3710
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="provider-wizard-generated-files"></a>Созданные мастером поставщика файлы
Мастер поставщика ATL OLE DB создает следующие файлы. В последующих разделах используется короткое имя «MyProvider», но конкретные имена файлов зависят от выбора, внесенные при создании поставщика.  
  
|Имя файла|Описание:|  
|---------------|-----------------|  
|MyProviderRS.cpp|Содержит вспомогательные команды `Execute` метод и сопоставления столбца поставщика.|  
|MyProviderDS.h|Реализует объект источника данных. Файл заголовка содержит сопоставление свойств для свойств источника данных.|  
|MyProviderRS.h|Реализует объекты команд и наборов строк. Файл заголовка содержит сопоставление свойств для свойств наборов строк и команд.|  
|MyProviderSess.h|Реализует объект сеанса. Файл заголовка содержит сопоставление свойств для свойств сеанса.|  
|MyProvider.rgs|Содержит зарегистрированные объекты, созданные мастером поставщика OLE DB.|  
  
## <a name="see-also"></a>См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)