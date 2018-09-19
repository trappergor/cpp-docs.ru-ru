---
title: Сопоставления свойств | Документация Майкрософт
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
ms.openlocfilehash: b3fb9c5a5c18925bfcd448bb2349379262b27361
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080991"
---
# <a name="property-maps"></a>Сопоставления свойств

Помимо сеанса, набор строк и дополнительных объектов команды каждый поставщик поддерживает одно или несколько свойств. Эти свойства определяются в сопоставлениях свойств, содержащихся в файлах заголовков, созданные мастером поставщика OLE DB. Каждый файл заголовка содержит схему для свойств в группе свойств OLE DB, определенные для объекта или объектов, определенных в этом файле. Файл заголовка, который содержит объект источника данных также содержит сопоставление свойств для [свойства DataSource](https://msdn.microsoft.com/library/ms724188\(v=vs.140\).aspx). Session.h содержит сопоставляемые свойства [свойства сеанса](/previous-versions/windows/desktop/ms714221\(v=vs.85\)). Объекты наборов строк и команд находятся в одном файле заголовка, вызывается *имя_проекта*RS.h. Эти свойства являются членами [свойства набора строк](/previous-versions/windows/desktop/ms711252\(v=vs.85\)) группы.  
  
## <a name="see-also"></a>См. также  

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)