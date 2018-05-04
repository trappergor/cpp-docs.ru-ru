---
title: Добавление страницы свойств ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c84cdabddb96d2deeecd09f26101e37d9c99d0ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="adding-an-atl-property-page"></a>Добавление страницы свойств ATL
Добавление страницы свойств Active Template Library (ATL) для проекта, проекта должны были созданы как приложение ATL или как приложение MFC с поддержкой ATL. Можно использовать [мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
 При добавлении страницы свойств для элемента управления, этот элемент управления должен поддерживать [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) интерфейса. По умолчанию этот интерфейс является производным списком элемента управления класса, если вы [Создание элемента управления ATL](../../atl/reference/adding-an-atl-control.md) с помощью [мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Если ваш класс элемента управления не имеет [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) в своем списке наследования, его необходимо добавить вручную.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>Добавление страницы свойств ATL в проект  
  
1.  В любом **обозревателе решений** или [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя проекта, к которому требуется добавить страницы свойств ATL.  
  
2.  В контекстном меню щелкните **добавить** и нажмите кнопку **Добавление класса**.  
  
3.  В [добавить класс](../../ide/add-class-dialog-box.md) щелкните в области шаблонов диалогового **страницы свойств ATL** и нажмите кнопку **откройте** для отображения [мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md).  
  
 После создания страницы свойств для элемента управления, необходимо предоставить [PROP_PAGE](property-map-macros.md#prop_page) записи в схеме сопоставления свойств для элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../../atl/atl-com-property-pages.md)   
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Пример. Реализация страницы свойств](../../atl/example-implementing-a-property-page.md)

