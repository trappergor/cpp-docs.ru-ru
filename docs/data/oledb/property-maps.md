---
title: Сопоставления свойств
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 0e1e9999c63bfa525988b67d020031fd76514b67
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415894"
---
# <a name="property-maps"></a>Сопоставления свойств

С сеансом, набор строк и дополнительных объектов команды каждый поставщик поддерживает одно или несколько свойств. Эти свойства определяются в сопоставления свойств, хранящихся в файлах заголовков, созданные **мастер поставщика OLE DB**. Каждый файл заголовка содержит схему для свойств в группе свойств OLE DB, определенные для объекта или объектов, определенных в этом файле. Файл заголовка, который содержит объект источника данных также содержит сопоставление свойств для [свойства DataSource](https://msdn.microsoft.com/library/ms724188). `Session.h` содержит сопоставление свойств для [свойства сеанса](/previous-versions/windows/desktop/ms714221(v=vs.85)). Объекты наборов строк и команд находятся в одном файле заголовка, вызывается *имя_проекта*RS.h. Эти свойства являются членами [свойства набора строк](/previous-versions/windows/desktop/ms711252(v=vs.85)) группы.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
