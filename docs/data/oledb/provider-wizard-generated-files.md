---
title: Созданные мастером поставщика файлы | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
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
ms.openlocfilehash: 40422ac7894523a28a2135b7f5005eb1f11d36c8
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216374"
---
# <a name="provider-wizard-generated-files"></a>Созданные мастером поставщика файлы

**Мастер поставщика ATL OLE DB** создает следующие файлы. Короткое имя используется в следующих разделах *Custom*, но конкретные имена файлов зависят от выбора, сделанного при создании поставщика.

|Имя файла|Описание|
|---------------|-----------------|
|*Custom*RS.cpp|Содержит поддержки команд `Execute` метод и сопоставления столбца поставщика.|
|*Custom*DS.h|Реализует объект источника данных. Файл заголовка содержит сопоставление свойств для свойства источника данных.|
|*Custom*RS.h|Реализует объекты команд и наборов строк. Файл заголовка содержит сопоставление свойств для свойств наборов строк и команд.|
|*Custom*Sess.h|Реализует объект сеанса. Файл заголовка содержит сопоставление свойств для свойств сеанса.|
|*Custom*.rgs|Содержит зарегистрированные объекты, создаваемые **мастер поставщика OLE DB**.|

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
