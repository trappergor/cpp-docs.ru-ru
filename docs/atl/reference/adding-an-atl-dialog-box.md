---
title: Добавление диалогового окна ATL | Документация Майкрософт
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
ms.openlocfilehash: 512f791b3db513c2a143bda84a8dc2677b341544
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106052"
---
# <a name="adding-an-atl-dialog-box"></a>Добавление диалогового окна ATL

Добавление диалогового окна ATL в проект, проект должен быть проекта ATL или в проект MFC, которая включает поддержку ATL. Вы можете использовать [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md), чтобы создать приложение ATL, или [добавить объект ATL в свое приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), чтобы реализовать поддержку ATL для приложения MFC.

По умолчанию мастер диалоговых окон ATL реализует диалоговое окно, производный от [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Этот класс поддерживает размещение элементов управления ActiveX и Windows. Если не требуется поддержка элементов управления ActiveX, затраты на после мастера создания кода, замените все вхождения `CAxDialogImpl` сочетанием [CSimpleDialog](../../atl/reference/csimpledialog-class.md) или [CDialogImpl](../../atl/reference/cdialogimpl-class.md) качестве базового класса .

> [!NOTE]
>  `CSimpleDialog` создает только модальные диалоговые окна, которые поддерживают только общие элементы управления Windows. `CDialogImpl` Создает модальное или немодальное диалоговые окна.

### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>Чтобы добавить ресурс диалогового окна ATL в проект

1. Создайте проект ATL с помощью [мастер проектов ATL](../../atl/reference/atl-project-wizard.md).

2. Из [представление классов](/visualstudio/ide/viewing-the-structure-of-code), щелкните правой кнопкой мыши имя проекта и нажмите кнопку **добавить** в контекстном меню. Нажмите кнопку **добавьте класс**.

3. В области шаблонов [Добавление класса](../../ide/add-class-dialog-box.md) диалоговом окне щелкните **диалогового окна ATL**. Нажмите кнопку **откройте** для отображения [мастер диалоговых окон ATL](../../atl/reference/atl-dialog-wizard.md).

Дополнительные сведения см. в разделе [реализация диалогового окна](../../atl/implementing-a-dialog-box.md).

## <a name="see-also"></a>См. также

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Классы окон](../../atl/atl-window-classes.md)<br/>
[Схемы сообщений](../../atl/message-maps-atl.md)

