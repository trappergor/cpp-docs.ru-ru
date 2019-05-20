---
title: Добавление страницы свойств ATL
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: 81f793fbdc6d9dda567051b8c35a96f3d3f2f470
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524618"
---
# <a name="adding-an-atl-property-page"></a>Добавление страницы свойств ATL

> [!NOTE] 
> Мастер страницы свойств в ATL недоступен в Visual Studio 2019 и более поздних версиях.

Чтобы добавить объект библиотеки шаблонных классов (ATL) на страницу свойств в проекте, необходимо создавать проект как COM-приложение ATL или приложение MFC с поддержкой ATL. Вы можете использовать [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md), чтобы создать приложение ATL, или [добавить объект ATL в свое приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), чтобы реализовать поддержку ATL для приложения MFC.

Если вы добавляете страницу свойств для элемента управления, ваш элемент управления должен поддерживать интерфейс [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md). По умолчанию этот интерфейс находится в списке деривации вашего класса управления, когда вы [создаете элемент управления ATL](../../atl/reference/adding-an-atl-control.md) с помощью [мастера управления ATL](../../atl/reference/atl-control-wizard.md).

> [!NOTE]
> Если ваш класс элемента управления не имеет [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) в списке деривации, необходимо добавить его вручную.

## <a name="to-add-an-atl-property-page-to-your-project"></a>Добавление страницы свойств ATL в проект

1. В **обозревателе решений** или [представлении классов](/visualstudio/ide/viewing-the-structure-of-code) щелкните правой кнопкой мыши имя проекта, в который вы хотите добавить страницу свойств ATL.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. В диалоговом окне [Добавить класс](../../ide/add-class-dialog-box.md) в области **Шаблоны** щелкните **страницу свойств ATL**, а затем щелкните **Открыть**, чтобы запустить [мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md).

После создания страницы свойств для элемента управления необходимо предоставить запись [PROP_PAGE](property-map-macros.md#prop_page) в схему сопоставления свойств для элемента управления.

## <a name="see-also"></a>См. также

[Страницы свойств](../../atl/atl-com-property-pages.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Пример: реализация страницы свойств](../../atl/example-implementing-a-property-page.md)
