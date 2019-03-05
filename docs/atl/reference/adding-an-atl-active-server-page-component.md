---
title: Добавление компонентов страницы активного сервера ATL
ms.date: 11/04/2016
helpviewer_keywords:
- ASP components, adding
- ASP components
- ATL, ASP components
- ATL ASP components
ms.assetid: 7be2204c-6e58-4099-8892-001b848c8987
ms.openlocfilehash: 2f7ad08cb514e33224c877bcbf1c5e8128e26185
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269842"
---
# <a name="adding-an-atl-active-server-page-component"></a>Добавление компонентов страницы активного сервера ATL

Чтобы добавить объект Active Template Library (ATL) в проект, проект должен будут созданы как ATL COM-приложение или приложение MFC с поддержкой ATL. Можно использовать [мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL, можно выбрать **Добавление поддержки ATL в MFC** из [класс диалоговое окно Добавление](../../ide/add-class-dialog-box.md) диалогового окна, или вы можете [Добавление объекта ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.

ASP-компоненты являются частью архитектуры служб IIS, который предоставляет следующие дополнительные возможности веб-разработки:

- ASP-компоненты можно внедрять в HTML-страницы для создания динамического содержимого зависит от обозревателя.

- ASP-страницах можно использовать для подключения к базам данных на основе стандартов.

- Можно использовать функции обработки ошибок ASP для веб-приложений.

## <a name="to-add-an-atl-active-server-pages-component-to-your-project"></a>Чтобы добавить компонент ATL Active Server Pages в проект

1. В **обозревателе решений** щелкните правой кнопкой мыши имя проекта, к которому вы хотите добавить компонент ATL ASP-страницы.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. В [Добавление класса](../../ide/add-class-dialog-box.md) отображаемое в диалоговом окне **шаблоны** панели щелкните **компонент библиотеки ATL**и нажмите кнопку **откройте** для отображения [Мастер компонентов страницы активного сервера ATL](../../atl/reference/atl-active-server-page-component-wizard.md).

## <a name="see-also"></a>См. также

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление нового интерфейса в проект ATL](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[Добавление точек подключения к объектам](../../atl/adding-connection-points-to-an-object.md)<br/>
[Добавление метода](../../ide/adding-a-method-visual-cpp.md)<br/>
[Класс MFC](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Добавление универсального класса C++](../../ide/adding-a-generic-cpp-class.md)
