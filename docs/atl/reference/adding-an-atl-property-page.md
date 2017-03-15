---
title: "Добавление страницы свойств ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 7b6a6220a33890d99e6fb2bd81ce832b38720c50
ms.lasthandoff: 02/24/2017

---
# <a name="adding-an-atl-property-page"></a>Добавление страницы свойств ATL
Добавление в проект страницу свойств Active Template Library (ATL), проект должен создан как приложение ATL или как приложение MFC с поддержкой ATL. Можно использовать [ATL Project Wizard](../../atl/reference/atl-project-wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
 При добавлении страницы свойств для элемента управления, элемент управления должен поддерживать [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) интерфейса. По умолчанию этот интерфейс является производным списком управления класс, если вы [Создание элемента управления ATL](../../atl/reference/adding-an-atl-control.md) с помощью [мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Если нет класса элемента управления [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) в своем списке наследования, его необходимо добавить вручную.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>Добавление страницы свойств ATL в проект  
  
1.  В любом **обозревателе решений** или [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя проекта, к которому требуется добавить страницы свойств ATL.  
  
2.  В контекстном меню щелкните **добавить** и нажмите кнопку **добавить класс**.  
  
3.  В [добавить класс](../../ide/add-class-dialog-box.md) диалогового окна, в области «Шаблоны» выберите **страницы свойств ATL** и нажмите кнопку **откройте** для отображения [мастер создания страниц свойств ATL](../../atl/reference/atl-property-page-wizard.md).  
  
 После создания страницы свойств для элемента управления, необходимо предоставить [PROP_PAGE](http://msdn.microsoft.com/library/2155973e-b96c-4385-bf85-5d6112c969b8) записи в схеме сопоставления свойств для элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../../atl/atl-com-property-pages.md)   
 [Основы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Пример: Реализация страницы свойств](../../atl/example-implementing-a-property-page.md)


