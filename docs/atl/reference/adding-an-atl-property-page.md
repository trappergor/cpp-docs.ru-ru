---
title: Добавление страницы свойств ATL
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: c61f666865d3e1db4cdcf2dc6d3e07c2113a79c7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290024"
---
# <a name="adding-an-atl-property-page"></a>Добавление страницы свойств ATL

Добавление страницы свойств Active Template Library (ATL) в проект, проект должен будут созданы как приложение ATL или как приложение MFC с поддержкой ATL. Можно использовать [мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL или [Добавление объекта ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.

При добавлении страницы свойств для элемента управления, элемент управления должен поддерживать [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) интерфейс. По умолчанию этот интерфейс находится в списке наследования элемента управления класса, если вы [Создание элемента управления ATL](../../atl/reference/adding-an-atl-control.md) с помощью [мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md).

> [!NOTE]
> Если ваш класс элемента управления не имеет [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) в списке наследования, необходимо добавить его вручную.

## <a name="to-add-an-atl-property-page-to-your-project"></a>Добавление страницы свойств ATL в проект

1. В любом **обозревателе решений** или [представление классов](/visualstudio/ide/viewing-the-structure-of-code), щелкните правой кнопкой мыши имя проекта, к которому вы хотите добавить страницы свойств ATL.

1. В контекстном меню, щелкните **добавить** и нажмите кнопку **Добавление класса**.

1. В [Добавление класса](../../ide/add-class-dialog-box.md) отображаемое в диалоговом окне **шаблоны** панели щелкните **страницы свойств ATL** и нажмите кнопку **откройте** для отображения [Мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md).

После создания страницы свойств для элемента управления, необходимо предоставить [PROP_PAGE](property-map-macros.md#prop_page) записи в схеме сопоставления свойств для элемента управления.

## <a name="see-also"></a>См. также

[Страницы свойств](../../atl/atl-com-property-pages.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Пример: Реализация страницы свойств](../../atl/example-implementing-a-property-page.md)
