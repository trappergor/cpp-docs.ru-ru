---
title: Добавление диалогового окна ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0883b87ce991b08a96b1d10b4acedf8562022a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="adding-an-atl-dialog-box"></a>Добавление диалогового окна ATL
Чтобы добавить диалоговое окно ATL в проект, проект должен быть проекта ATL или проект MFC с поддержкой ATL. Можно использовать [мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
 По умолчанию мастер диалоговых окон ATL реализует диалоговое окно, производный от [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Этот класс поддерживает размещение элементов управления ActiveX и Windows. Если нежелательно издержки, связанные с поддержкой элементов управления ActiveX, после создания кода мастером замените все вхождения `CAxDialogImpl` либо [CSimpleDialog](../../atl/reference/csimpledialog-class.md) или [CDialogImpl](../../atl/reference/cdialogimpl-class.md) качестве базового класса .  
  
> [!NOTE]
>  `CSimpleDialog` создает только модальные диалоговые окна, поддерживающие только общие элементы управления Windows. `CDialogImpl` Создает модальные и немодальные диалоговые окна.  
  
### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>Чтобы добавить ресурс диалогового окна ATL в проект  
  
1.  Создайте проект ATL с помощью [мастер проектов ATL](../../atl/reference/atl-project-wizard.md).  
  
2.  Из [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя проекта и нажмите кнопку **добавить** в контекстном меню. Нажмите кнопку **добавьте класс**.  
  
3.  В области шаблонов [добавить класс](../../ide/add-class-dialog-box.md) диалоговое окно, нажмите кнопку **диалог ATL**. Нажмите кнопку **откройте** для отображения [мастер диалоговых окон ATL](../../atl/reference/atl-dialog-wizard.md).  
  
 Дополнительные сведения см. в разделе [реализация диалогового](../../atl/implementing-a-dialog-box.md).  
  
## <a name="see-also"></a>См. также  
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Классы окон](../../atl/atl-window-classes.md)   
 [Схемы сообщений](../../atl/message-maps-atl.md)

