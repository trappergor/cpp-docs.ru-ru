---
title: 'Контейнеры элементов ActiveX: Просмотр и изменение свойств элементов управления | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9614ecfcd23418f8b0abc08622e8c272bb5548a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388827"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>Контейнеры элементов управления ActiveX. Просмотр и изменение свойств элементов управления

При вставке элемента управления ActiveX в проект, бывает полезно для просмотра и изменения свойств, поддерживаемых элементом управления ActiveX. В этой статье описывается использование редактора ресурсов Visual C++ для этого.

Если приложение контейнера элемента управления ActiveX использует внедренные элементы управления, можно Просмотр и изменение свойств элемента управления в редакторе ресурсов. Можно также использовать редактор ресурсов для задания значений свойств во время разработки. Редактор ресурсов автоматически сохранит эти значения в файле ресурсов проекта. Любой экземпляр элемента управления будет иметь его свойствами, инициализируемыми равными эти значения.

Эта процедура предполагает, что вы вставили элемент управления в проект. Сведения см. в разделе [контейнеры элементов управления ActiveX: Вставка элемента управления в приложение контейнера элемента управления](../mfc/inserting-a-control-into-a-control-container-application.md).

Просмотр свойств элемента управления первым делом для добавления экземпляра элемента управления для шаблона диалогового окна проекта.

### <a name="to-view-the-properties-of-a-control"></a>Чтобы просмотреть свойства элемента управления

1. В представлении ресурсов, откройте **диалоговое окно** папки.

1. Откройте ваш шаблон главного диалогового окна.

1. Вставка элемента управления ActiveX с помощью **Вставка элемента ActiveX** диалоговое окно. Дополнительные сведения см. в разделе [просмотра и добавление элементов управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

1. Выберите элемент управления ActiveX в диалоговом окне.

1. В окне «Свойства» щелкните **свойства** кнопки.

Используйте **свойства** диалоговое окно для изменения и сразу же протестировать новые свойства.

## <a name="see-also"></a>См. также

[Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

