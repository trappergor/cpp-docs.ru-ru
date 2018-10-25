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
ms.openlocfilehash: a9bc7c85dccdfe095412450d5020fc8a6b42d516
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076975"
---
# <a name="provider-wizard-generated-files"></a>Созданные мастером поставщика файлы

Мастер поставщика ATL OLE DB создает следующие файлы. Короткое имя используется в следующих разделах *Custom*, но конкретные имена файлов зависят от выбора, сделанного при создании поставщика.

|Имя файла|Описание|
|---------------|-----------------|
|*Custom*RS.cpp|Содержит поддержки команд `Execute` метод и сопоставления столбца поставщика.|
|*Custom*DS.h|Реализует объект источника данных. Файл заголовка содержит сопоставление свойств для свойства источника данных.|
|*Custom*RS.h|Реализует объекты команд и наборов строк. Файл заголовка содержит сопоставление свойств для свойств наборов строк и команд.|
|*Custom*Sess.h|Реализует объект сеанса. Файл заголовка содержит сопоставление свойств для свойств сеанса.|
|*Custom*.rgs|Содержит зарегистрированные объекты, созданные мастером поставщика OLE DB.|

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)