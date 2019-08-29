---
title: Добавление поддержки ATL в проект MFC
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: fba79db013cd9f4cc62ba5826b53e5fa9b15c83a
ms.sourcegitcommit: bf1940a39029dbbd861f95480f55e5e8bd25cda0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70108413"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в проект MFC

Если вы уже создали приложение на основе MFC, то можете легко добавить поддержку библиотеки ATL с помощью интегрированной среды разработки.

> [!NOTE]
>  Эта поддержка действует только для простых COM-объектов, добавленных в исполняемый файл MFC или проект библиотеки DLL. В проекты MFC можно добавить другие COM-объекты (включая элементы управления ActiveX), но эти объекты могут работать не так, как ожидалось.

::: moniker range=">=vs-2019"

1. В обозреватель решений щелкните правой кнопкой мыши узел проекта.

1. В контекстном меню выберите **Добавить** и **Новый элемент**.

1. В левой области выберите **ATL** , а затем в центральной области выберите **поддержка ATL** .

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-add-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в проект MFC

1. В обозреватель решений щелкните правой кнопкой мыши узел проекта.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. Выберите **ATL** в левой области, а затем щелкните **Добавить поддержку ATL в проект MFC** в центральной области.

::: moniker-end

Дополнительные сведения о том, как добавление поддержки ATL изменяет код проекта MFC, см. [в разделе сведения о поддержке ATL, добавленной мастером ATL](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md) .

## <a name="see-also"></a>См. также

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Перемещение по структуре класса](../../ide/navigate-code-cpp.md)
