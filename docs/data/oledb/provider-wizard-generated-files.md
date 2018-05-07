---
title: Созданные мастером поставщика файлы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac23f06bf1ae697ecd627d493aa5902219488138
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="provider-wizard-generated-files"></a>Созданные мастером поставщика файлы
Мастер поставщика ATL OLE DB создает следующие файлы. В последующих разделах используется короткое имя «MyProvider», но конкретные имена файлов зависят от выбора, внесенные при создании поставщика.  
  
|Имя файла|Описание|  
|---------------|-----------------|  
|MyProviderRS.cpp|Содержит вспомогательные команды `Execute` метод и сопоставления столбца поставщика.|  
|MyProviderDS.h|Реализует объект источника данных. Файл заголовка содержит сопоставление свойств для свойств источника данных.|  
|MyProviderRS.h|Реализует объекты команд и наборов строк. Файл заголовка содержит сопоставление свойств для свойств наборов строк и команд.|  
|MyProviderSess.h|Реализует объект сеанса. Файл заголовка содержит сопоставление свойств для свойств сеанса.|  
|MyProvider.rgs|Содержит зарегистрированные объекты, созданные мастером поставщика OLE DB.|  
  
## <a name="see-also"></a>См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)