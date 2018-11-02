---
title: Добавление поддержки ATL в проект MFC
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 9f8861e3b6aa0fee95aa84b989cf1057ae0f76b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448607"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в проект MFC

Если вы уже создали приложение на базе MFC, затем можно добавить поддержку для Active Template Library (ATL) легко, выполнив добавления поддержки ATL, MFC мастер проекта.

> [!NOTE]
>  ATL и MFC не поддерживаются обычно в выпусках Express Visual Studio.

> [!NOTE]
>  Эта поддержка действует только для простых COM-объектов, добавленных в исполняемый файл MFC или проект библиотеки DLL. Проекты MFC можно добавить другие COM-объекты (включая элементы управления ActiveX), но объекты могут не работать должным образом.

### <a name="to-add-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в проект MFC

1. В обозревателе решений щелкните правой кнопкой мыши проект, к которому вы хотите добавить поддержку ATL.

1. В контекстном меню, щелкните **добавить**, а затем нажмите кнопку **Добавление класса**.

1. Выберите **Добавление поддержки ATL в проект MFC** значок.

    > [!NOTE]
    >  Этот значок расположен в папке ATL в **категории** области.

1. При появлении запроса, щелкните **Да** Добавление поддержки ATL.

Дополнительные сведения о том, как добавление поддержки ATL изменяет код проекта MFC, см. в разделе [сведения об ATL поддерживает Added мастером ATL](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)

## <a name="see-also"></a>См. также

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
