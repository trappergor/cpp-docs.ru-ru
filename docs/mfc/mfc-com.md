---
title: MFC COM
ms.date: 09/12/2018
f1_keywords:
- MFC COM (MFC)
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
ms.openlocfilehash: 514251475050e728be1959417ead1dbdf96e4800
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358202"
---
# <a name="mfc-com"></a>MFC COM

Подмножество MFC предназначено для поддержки COM, в то время как большая часть Библиотеки активных шаблонов (ATL) предназначена для программирования COM. В этом разделе тем описывается поддержка MFC COM.

Активные технологии (такие как элементы управления ActiveX, активное сдерживание документов, OLE и т.д.) используют модель компонентного объекта (COM), чтобы компоненты программного обеспечения взаимодействовали друг с другом в сетевой среде, независимо от языка, с которым они были созданы. Активные технологии могут быть использованы для создания приложений, которые работают на рабочем столе или в Интернете. Для получения дополнительной информации [см. Введение](../atl/introduction-to-com.md) в COM или [модель компонентного объекта](/windows/win32/com/the-component-object-model).

Активные технологии включают в себя как клиентские, так и серверные технологии, в ключая:

- Элементы управления ActiveX — это интерактивные объекты, которые могут использоваться в контейнерах, таких как веб-узел. Для получения дополнительной информации о элементах управления ActiveX см.:

  - [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

  - [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md)

  - [Обзор: Интернет](../mfc/mfc-internet-programming-basics.md)

  - [Обновление существующего управления ActiveX, который будет использоваться в Интернете](../mfc/upgrading-an-existing-activex-control.md)

  - [Отладка управления ActiveX](/visualstudio/debugger/how-to-debug-an-activex-control)

- Активный скрипт управляет интегрированным поведением одного или нескольких элементов управления ActiveX из браузера или сервера. Для получения дополнительной информации об активных сценариях, [см.](../mfc/active-technology-on-the-internet.md)

- [Автоматизация](../mfc/automation.md) (ранее известная как OLE Automation) позволяет одному приложению манипулировать объектами, реализованными в другом приложении, или «разоблачать» объекты, чтобы ими можно было манипулировать.

   Автоматизированный объект может быть локальным или удаленным (на другой машине, доступной через сеть). Автоматизация доступна для OLE- и COM-объектов.

- В этом разделе также содержится информация о том, как писать компоненты COM с помощью MFC, например, в [точках подключения.](../mfc/connection-points.md)

Для обсуждения того, что до сих пор называется OLE по [OLE](../mfc/ole-in-mfc.md)сравнению с тем, что сейчас называется активной технологии, см.

## <a name="in-this-section"></a>в этом разделе

[Вложение активного документа](../mfc/active-document-containment.md)

[Служба автоматизации](../mfc/automation.md)

[Точки подключения](../mfc/connection-points.md)

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>См. также раздел

[Основные понятия](../mfc/mfc-concepts.md)
