---
title: MFC COM | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MFC COM (MFC)
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d23a9be38ebb870adf098b34fac79afff6345cd8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394748"
---
# <a name="mfc-com"></a>MFC COM

Подмножества MFC предназначен для поддержки модели COM, хотя большинство из Active Template Library (ATL) предназначается для программирования COM. Разделы в этом разделе описывается поддержка MFC для модели COM.

Активных технологий (например, ActiveX элементов управления, вложение активного документа, OLE и т. д.) используйте модель объектов компонентов (COM), чтобы включить программным компонентам взаимодействовать друг с другом в сетевой среде, независимо от языка, с которым они были создан. Активных технологий может использоваться для создания приложений, работающих на рабочем столе или в Интернете. Дополнительные сведения см. в разделе [введение в модель COM](../atl/introduction-to-com.md) или [это модель объекта компонента](/windows/desktop/com/the-component-object-model).

Активных технологий включают клиентских и серверных технологий, включая следующие:

- Элементы управления ActiveX являются интерактивных объектов, которые могут использоваться в контейнерах, например веб-сайта. Дополнительные сведения для элементов управления ActiveX см. в разделе:

   - [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

   - [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md)

   - [Обзор: Интернет](../mfc/mfc-internet-programming-basics.md)

   - [Обновление существующего элемента управления ActiveX для использования в Интернете](../mfc/upgrading-an-existing-activex-control.md)

   - [Отладка элемента управления ActiveX](/visualstudio/debugger/how-to-debug-an-activex-control)

- Активные сценарии управляет поведением интегрированной один или несколько элементов управления ActiveX из браузера или сервера. Дополнительные сведения об активных скриптов, см. в разделе [Технология Active в Интернете](../mfc/active-technology-on-the-internet.md).

- [Автоматизация](../mfc/automation.md) (ранее известные как OLE-автоматизация) делает возможным для одного приложения для управления объектами, реализованными в другом приложении, или для «представления» объектов, поэтому ими можно управлять.

     Автоматизированный объект может быть локальным или удаленным (на другом компьютере, доступном по сети). Автоматизация доступна для OLE- и COM-объектов.

- Здесь также приведены сведения о том, как создавать компоненты COM, с помощью MFC, например, в [точек подключения](../mfc/connection-points.md).

Обсуждение по-прежнему так называемая OLE и то, что теперь называется active-технология, см. в разделах [OLE](../mfc/ole-in-mfc.md).

Кроме того, см. в статье базы знаний Q248019: HOWTO: предотвратить сервер занят диалогового окна поле из отображаются во время длительной COM операции.

## <a name="in-this-section"></a>В этом разделе

[Вложение активного документа](../mfc/active-document-containment.md)

[Автоматизация](../mfc/automation.md)

[Точки подключения](../mfc/connection-points.md)

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)

