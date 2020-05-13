---
title: Добавление поддержки ATL в проект MFC
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 05c4e8ba54d9a573b422f136c9e8cf69e48d1c9a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371682"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в проект MFC

Если вы уже создали приложение на основе MFC, то вы можете легко добавить поддержку для Библиотеки Active Template Library (ATL) с помощью IDE.

> [!NOTE]
> Эта поддержка действует только для простых COM-объектов, добавленных в исполняемый файл MFC или проект библиотеки DLL. Вы можете добавить другие объекты COM (включая элементы управления ActiveX) в проекты MFC, но объекты могут работать не так, как ожидалось.

::: moniker range=">=vs-2019"

1. В Solution Explorer щелкните правым щелкните узла проекта.

1. В контекстном меню выберите **Добавить** и **Новый элемент**.

1. Выберите **ATL** в левом стеле, а затем выберите **поддержку ATL** в центральной панели.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-add-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в ваш проект MFC

1. В Solution Explorer щелкните правым щелкните узла проекта.

1. В меню ярлыка нажмите **Добавить,** а затем нажмите **Добавить класс**.

1. Выберите **ATL** в левом стекле, а затем выберите **Добавить поддержку ATL** в проект MFC в центральной панели.

::: moniker-end

Для получения дополнительной информации о том, как добавление поддержки ATL изменяет код проекта MFC, [см.](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)

## <a name="see-also"></a>См. также раздел

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Перемещение по структуре класса](../../ide/navigate-code-cpp.md)
