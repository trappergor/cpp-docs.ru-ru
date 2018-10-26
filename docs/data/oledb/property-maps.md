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
ms.openlocfilehash: bbed70f7871cb215a944a5143793b26b4196d7bc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052760"
---
# <a name="property-maps"></a>Сопоставления свойств

Помимо сеанса, набор строк и дополнительных объектов команды каждый поставщик поддерживает одно или несколько свойств. Эти свойства определяются в сопоставлениях свойств, содержащихся в файлах заголовков, созданные мастером поставщика OLE DB. Каждый файл заголовка содержит схему для свойств в группе свойств OLE DB, определенные для объекта или объектов, определенных в этом файле. Файл заголовка, который содержит объект источника данных также содержит сопоставление свойств для [свойства DataSource](https://msdn.microsoft.com/library/ms724188). Session.h содержит сопоставляемые свойства [свойства сеанса](/previous-versions/windows/desktop/ms714221). Объекты наборов строк и команд находятся в одном файле заголовка, вызывается *имя_проекта*RS.h. Эти свойства являются членами [свойства набора строк](/previous-versions/windows/desktop/ms711252) группы.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)