---
title: Добавление ASP-компонента ATL
ms.date: 05/09/2019
ms.assetid: 7be2204c-6e58-4099-8892-001b848c8987
ms.openlocfilehash: a84eeb20f047097e3dbb3c7f3bb5f5a12b069bcb
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075300"
---
# <a name="adding-an-atl-active-server-page-component"></a>Добавление ASP-компонента ATL

::: moniker range="vs-2019"

Мастер ASP-компонентов ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=vs-2017"

Чтобы добавить объект библиотеки шаблонных классов (ATL) в проект, необходимо создавать проект как COM-приложение ATL или приложение MFC с поддержкой ATL. Вы можете использовать [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL, выбрать пункт **Добавить в MFC поддержку ATL** в диалоговом окне [Добавить класс](../../ide/add-class-dialog-box.md), либо [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), чтобы реализовать поддержку ATL для приложения MFC.

ASP-компоненты входят в состав архитектуры служб IIS, которая реализует следующие дополнительные возможности веб-разработки.

- Внедрение ASP-компонентов на HTML-страницы для создания динамического содержимого, не зависящего от браузера.

- Использование ASP-страниц для обеспечения подключений к базе данных на основе стандартов.

- Использование возможностей обработки ошибок ASP для веб-приложений.

## <a name="to-add-an-atl-active-server-pages-component-to-your-project"></a>Добавление ASP-компонента ATL в проект

1. В **обозревателе решений** щелкните правой кнопкой мыши имя проекта, в который вы хотите добавить ASP-компонент ATL.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. В диалоговом окне [Добавить класс](../../ide/add-class-dialog-box.md) в области **Шаблоны** щелкните **ASP-компонент библиотеки ATL**, а затем щелкните **Открыть**, чтобы запустить [мастер ASP-компонентов ATL](../../atl/reference/atl-active-server-page-component-wizard.md).

::: moniker-end

## <a name="see-also"></a>См. также:

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление нового интерфейса в проект ATL](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[Добавление точек подключения к объектам](../../atl/adding-connection-points-to-an-object.md)<br/>
[Добавление метода](../../ide/adding-a-method-visual-cpp.md)<br/>
[Класс MFC](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Добавление универсального класса C++](../../ide/adding-a-generic-cpp-class.md)
