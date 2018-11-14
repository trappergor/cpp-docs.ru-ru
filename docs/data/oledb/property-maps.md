---
title: Сопоставления свойств
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 2d01c2f0d7fb581f9f7e93c1ec100e465a6d92f3
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556490"
---
# <a name="property-maps"></a>Сопоставления свойств

С сеансом, набор строк и дополнительных объектов команды каждый поставщик поддерживает одно или несколько свойств. Эти свойства определяются в сопоставления свойств, хранящихся в файлах заголовков, созданные **мастер поставщика OLE DB**. Каждый файл заголовка содержит схему для свойств в группе свойств OLE DB, определенные для объекта или объектов, определенных в этом файле. Файл заголовка, который содержит объект источника данных также содержит сопоставление свойств для [свойства DataSource](https://msdn.microsoft.com/library/ms724188). `Session.h` содержит сопоставление свойств для [свойства сеанса](https://docs.microsoft.com/previous-versions/windows/desktop/ms714221(v=vs.85)). Объекты наборов строк и команд находятся в одном файле заголовка, вызывается *имя_проекта*RS.h. Эти свойства являются членами [свойства набора строк](https://docs.microsoft.com/previous-versions/windows/desktop/ms711252(v=vs.85)) группы.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
