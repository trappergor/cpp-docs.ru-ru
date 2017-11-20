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
ms.openlocfilehash: 24da0ab4b3ab27cdb9a70c0f9cc05e3ca86e117d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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