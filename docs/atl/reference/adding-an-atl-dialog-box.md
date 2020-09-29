---
title: Добавление диалогового окна ATL
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
ms.openlocfilehash: 71290cf0763ac6594985acc4cb11562efe7028e6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499375"
---
# <a name="adding-an-atl-dialog-box"></a>Добавление диалогового окна ATL

Чтобы добавить в проект диалоговое окно ATL, проект должен быть либо проектом ATL, либо проектом MFC, включающим поддержку ATL. Можно использовать [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL или [Добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL для приложения MFC.

По умолчанию мастер диалоговых окон ATL реализует диалоговое окно, производное от [каксдиалогимпл](../../atl/reference/caxdialogimpl-class.md). Этот класс включает поддержку размещения элементов управления ActiveX и Windows. Если вы не хотите издержки в поддержке элементов управления ActiveX, после того, как мастер создал ваш код, замените все экземпляры `CAxDialogImpl` на [Ксимпледиалог](../../atl/reference/csimpledialog-class.md) или [CDialogImpl](../../atl/reference/cdialogimpl-class.md) в качестве базового класса.

> [!NOTE]
> `CSimpleDialog` создает только модальные диалоговые окна, поддерживающие только общие элементы управления Windows. `CDialogImpl` создает модальные или немодальные диалоговые окна.

## <a name="to-add-an-atl-dialog-resource-to-your-project"></a>Добавление ресурса диалогового окна ATL в проект

1. Создайте проект ATL с помощью [мастера проектов ATL](../../atl/reference/atl-project-wizard.md).

1. В [представление классов](/visualstudio/ide/viewing-the-structure-of-code)щелкните правой кнопкой мыши имя проекта и в контекстном меню выберите команду **Добавить** . Нажмите **Добавить класс**.

1. В области **шаблоны** диалогового окна [Добавление класса](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) выберите пункт **диалоговое окно ATL**. Нажмите кнопку **Открыть** , чтобы открыть [Мастер диалоговых окон ATL](../../atl/reference/atl-dialog-wizard.md).

Дополнительные сведения см. [в разделе Реализация диалогового окна](../../atl/implementing-a-dialog-box.md).

## <a name="see-also"></a>См. также раздел

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Классы окон](../../atl/atl-window-classes.md)<br/>
[Схемы сообщений](../../atl/message-maps-atl.md)
