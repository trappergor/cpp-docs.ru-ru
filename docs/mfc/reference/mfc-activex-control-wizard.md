---
title: мастер элементов управления MFC ActiveX
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.mfc.ctl.overview
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
ms.openlocfilehash: 3341f840c46584c4e45afe3607c83433976e6c37
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217646"
---
# <a name="mfc-activex-control-wizard"></a>мастер элементов управления MFC ActiveX

Элемент управления ActiveX имеет определенный тип [сервера автоматизации](../../mfc/automation-servers.md); это повторно используемый компонент. Приложение размещения элемента управления ActiveX [клиента автоматизации](../../mfc/automation-clients.md) этого элемента управления. Если вашей целью является создание повторно используемого компонента, затем используйте этот мастер для создания элемента управления. См. в разделе [элементы ActiveX в MFC](../../mfc/mfc-activex-controls.md) Дополнительные сведения.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](../activex-controls.md).

Кроме того, можно создать автоматизации server MFC приложения с помощью [мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md).

Элемент управления ActiveX, созданных с помощью этого мастера может иметь пользовательский интерфейс, или он может быть скрытым. Можно указать этот параметр в [параметры управления](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницу мастера. Элемент управления timer является примером элемента управления ActiveX, который будет невидимым.

Элементы управления ActiveX могут иметь сложного пользовательского интерфейса. Некоторые элементы управления могут быть как инкапсулированные формы: один элемент управления, содержащий множество полей, каждое элемент управления Windows сама по себе. Например объект автомобильных запчастей, реализован как элемент управления MFC ActiveX может представлять различные пользовательский интерфейс, через который пользователи могут читать и изменять номер части, имя и другие сведения. См. в разделе [элементы ActiveX в MFC](../../mfc/mfc-activex-controls.md) Дополнительные сведения.

Если вам нужно создать контейнер для объектов ActiveX, см. в разделе [Создание контейнера элемента управления ActiveX](../../mfc/reference/creating-an-mfc-activex-control-container.md).

Начальная программа MFC включает в себя (.cpp) исходные файлы C++, файлы ресурсов (.rc) и файл проекта (VCXPROJ-файл). Код, созданный в этих начальный набор файлов зависит от MFC.

В следующем списке примера показаны задачи и типы расширений для элемента управления ActiveX:

- [Оптимизация элемента управления ActiveX](../../mfc/mfc-activex-controls-optimization.md)

- [Добавление событий хранения в элемент управления ActiveX](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [Добавление пользовательских событий](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [Добавление стандартных методов](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [Добавление пользовательских методов](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [Добавление стандартных свойств](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [Добавление пользовательских свойств](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [Программирование элементов управления ActiveX в контейнере элементов управления ActiveX](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>Обзор

На этой странице мастера описываются текущие параметры приложения для создаваемого проекта элемента управления ActiveX в MFC. По умолчанию мастер создает проект следующим образом:

- Проект по умолчанию создает файлы лицензий или справки не во время выполнения. Эти параметры по умолчанию можно изменить на [параметры приложения](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) страницы. Только выбранные элементы, на этой странице мастера элементов управления ActiveX, отражаются **Обзор** страницы.

- Проект содержит класс элемента управления и класс страницы свойств, на основе имени проекта. Можно изменить имена из имен проекта и файла на [имена элементов управления](../../mfc/reference/control-names-mfc-activex-control-wizard.md) страницы.

- Элемент управления основан на существующем элементе управления Windows, активируется, когда он становится видимым и включает **о** диалоговое окно. Эти параметры по умолчанию можно изменить на [параметры управления](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы.

## <a name="see-also"></a>См. также

[Проекты Visual Studio — C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[C++типы проектов в Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Основные понятия](../../atl/active-template-library-atl-concepts.md)
