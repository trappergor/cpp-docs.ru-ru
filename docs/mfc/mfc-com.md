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
ms.openlocfilehash: da194510938e3fe02eba5993182e811fdf2e1b7c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618015"
---
# <a name="mfc-com"></a>MFC COM

Подмножество MFC предназначено для поддержки модели COM, а большая часть библиотеки шаблонов Active Template (ATL) предназначена для программирования COM. В этом разделе разделов описывается поддержка MFC для модели COM.

Активные технологии (такие как элементы управления ActiveX, включение активных документов, OLE и т. д.) используют модель COM, чтобы обеспечить взаимодействие компонентов программного обеспечения друг с другом в сетевой среде, независимо от языка, с которым они были созданы. Активные технологии можно использовать для создания приложений, которые выполняются на настольном компьютере или в Интернете. Дополнительные сведения см. в статье [Введение в модель COM](../atl/introduction-to-com.md) или [объектной модели компонента](/windows/win32/com/the-component-object-model).

В число активных технологий входят клиентские и серверные технологии, включая следующие:

- Элементы управления ActiveX — это интерактивные объекты, которые можно использовать в таких контейнерах, как веб-сайт. Дополнительные сведения об элементах управления ActiveX см. в следующих статьях:

  - [Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)

  - [Элементы управления ActiveX в Интернете](activex-controls-on-the-internet.md)

  - [Обзор: Интернет](mfc-internet-programming-basics.md)

  - [Обновление существующего элемента управления ActiveX для использования в Интернете](upgrading-an-existing-activex-control.md)

  - [Отладка элемента управления ActiveX](/visualstudio/debugger/how-to-debug-an-activex-control)

- Активный сценарий управляет встроенным поведением одного или нескольких элементов управления ActiveX из браузера или с сервера. Дополнительные сведения о активных сценариях см. в статье об [активных технологиях в Интернете](active-technology-on-the-internet.md).

- [Автоматизация](automation.md) (ранее известная как OLE-автоматизация) позволяет одному приложению манипулировать объектами, реализованными в другом приложении, или "предоставлять" объекты, чтобы их можно было манипулировать.

   Автоматизированный объект может быть локальным или удаленным (на другом компьютере, доступном по сети). Автоматизация доступна для OLE- и COM-объектов.

- В этом разделе также приводятся сведения о том, как писать COM-компоненты с помощью MFC, например в [точках подключения](connection-points.md).

Обсуждение того, что все еще называется OLE, и что теперь называется Active Technology, см. в разделах, посвященных [OLE](ole-in-mfc.md).

## <a name="in-this-section"></a>В этом разделе

[Вложение активного документа](active-document-containment.md)

[Служба автоматизации](automation.md)

[Точки подключения](connection-points.md)

[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)

## <a name="see-also"></a>См. также раздел

[Концепции](mfc-concepts.md)
