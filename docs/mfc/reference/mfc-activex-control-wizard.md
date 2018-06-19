---
title: Мастер элементов управления ActiveX MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.overview
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45af43a98244e90f52075817fc9e17a905cbf065
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375067"
---
# <a name="mfc-activex-control-wizard"></a>мастер элементов управления MFC ActiveX
Элемент управления ActiveX — это определенный тип [сервера автоматизации](../../mfc/automation-servers.md); это повторно используемый компонент. Размещение элемента управления ActiveX приложения является [клиента автоматизации](../../mfc/automation-clients.md) этого элемента управления. Если вашей целью является создание многократно используемых компонентов, используйте этот мастер для создания элемента управления. В разделе [элементы управления MFC ActiveX](../../mfc/mfc-activex-controls.md) для получения дополнительной информации.  
  
 Кроме того, можно создать автоматизации сервером MFC приложения с помощью [мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md).  
  
 Элемент управления ActiveX, созданный с помощью этого мастера может иметь пользовательский интерфейс, или он может быть скрытым. Можно указать этот параметр в [параметры управления](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницу мастера. Элемент управления timer приведен пример элемента управления ActiveX, который требуется быть скрытым.  
  
 Элементы управления ActiveX могут иметь сложного пользовательского интерфейса. Некоторые элементы управления могут быть как инкапсулированные формы: один элемент управления, содержащий множество полей, каждое элемент управления Windows сама по себе. Например объект автомобильных запчастей, реализован как элемент управления MFC ActiveX могут представлять формы пользовательским интерфейсом, через который пользователи могут читать и изменять номер части, имя и другие сведения. В разделе [элементы управления MFC ActiveX](../../mfc/mfc-activex-controls.md) для получения дополнительной информации.  
  
 Если вам нужно создать контейнер для объектов ActiveX, см. раздел [Создание контейнера элемента управления ActiveX](../../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
 Начальная программа MFC включает (.cpp) исходные файлы C++, файлы ресурсов (RC) и файл проекта (VCXPROJ). Код, созданный в этих начальных файлах, основан на MFC.  
  
 На следующем образце списка показаны задачи и типы расширений элементов управления ActiveX:  
  
-   [Оптимизация элемента управления ActiveX](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [Добавление событий хранения в элемент управления ActiveX](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Добавление пользовательских событий](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [Добавление стандартных методов](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [Добавление пользовательских методов](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [Добавление стандартных свойств](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Добавление пользовательских свойств](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Программирование элементов управления ActiveX в контейнере элементов управления ActiveX](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## <a name="overview"></a>Обзор  
 На этой странице мастера описываются текущие параметры приложения для создаваемого проекта элемента управления ActiveX в MFC. По умолчанию мастер создает проект следующим образом:  
  
-   По умолчанию проект создает файлы лицензии или справки не во время выполнения. Эти параметры по умолчанию можно изменить на [параметры приложения](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) страницы. Только выбранные элементы, сделанные на этой странице мастера элементов управления ActiveX, отражаются на **Обзор** страницы.  
  
-   Проект содержит класс элемента управления и класса страницы свойств, на основе имени проекта. Можно изменить имена имен проекта и файла на [имена элементов управления](../../mfc/reference/control-names-mfc-activex-control-wizard.md) страницы.  
  
-   Элемент управления, основанный на существующем элементе управления Windows, активируется, когда он становится видимым и включает **о** диалоговое окно. Эти параметры по умолчанию можно изменить на [параметры управления](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы.  
  
## <a name="see-also"></a>См. также  
 [Создание проектов Visual C++ и управление ими](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)

