---
title: Созданные мастером поставщика файлы | Документация Майкрософт
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
ms.openlocfilehash: 26e20e0417e2253158930a8d3d055171fe767001
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108408"
---
# <a name="provider-wizard-generated-files"></a>Созданные мастером поставщика файлы

Мастер поставщика ATL OLE DB создает следующие файлы. Короткое имя «MyProvider» используется в следующих разделах, но конкретные имена файлов зависят от выбора, внесенные при создании поставщика.  
  
|Имя файла|Описание|  
|---------------|-----------------|  
|MyProviderRS.cpp|Содержит поддержки команд `Execute` метод и сопоставления столбца поставщика.|  
|MyProviderDS.h|Реализует объект источника данных. Файл заголовка содержит сопоставление свойств для свойства источника данных.|  
|MyProviderRS.h|Реализует объекты команд и наборов строк. Файл заголовка содержит сопоставление свойств для свойств наборов строк и команд.|  
|MyProviderSess.h|Реализует объект сеанса. Файл заголовка содержит сопоставление свойств для свойств сеанса.|  
|MyProvider.rgs|Содержит зарегистрированные объекты, созданные мастером поставщика OLE DB.|  
  
## <a name="see-also"></a>См. также  

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)