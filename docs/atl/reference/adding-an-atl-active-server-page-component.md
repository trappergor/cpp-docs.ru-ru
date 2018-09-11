---
title: Добавление компонентов страницы активного сервера ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ASP components, adding
- ASP components
- ATL, ASP components
- ATL ASP components
ms.assetid: 7be2204c-6e58-4099-8892-001b848c8987
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cf97db30cae44d02a690782f1246e06d6c2b9a8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766725"
---
# <a name="adding-an-atl-active-server-page-component"></a>Добавление компонентов страницы активного сервера ATL

Чтобы добавить объект Active Template Library (ATL) в проект, проект должен будут созданы как ATL COM-приложение или приложение MFC с поддержкой ATL. Можно использовать [мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL, можно выбрать **Добавление поддержки ATL в MFC** из [класс диалоговое окно Добавление](../../ide/add-class-dialog-box.md) диалогового окна, или вы можете [Добавление объекта ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.

ASP-компоненты являются частью архитектуры служб IIS, который предоставляет следующие дополнительные возможности веб-разработки:

- ASP-компоненты можно внедрять в HTML-страницы для создания динамического содержимого зависит от обозревателя.

- ASP-страницах можно использовать для подключения к базам данных на основе стандартов.

- Можно использовать функции обработки ошибок ASP для веб-приложений.

### <a name="to-add-an-atl-active-server-pages-component-to-your-project"></a>Чтобы добавить компонент ATL Active Server Pages в проект

1. В **обозревателе решений** щелкните правой кнопкой мыши имя проекта, к которому вы хотите добавить компонент ATL ASP-страницы.

2. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

3. В [Добавление класса](../../ide/add-class-dialog-box.md) диалоговом окне в области «Шаблоны» щелкните **компонент библиотеки ATL**, а затем нажмите кнопку **откройте** для отображения [активного сервера ATL Мастер компонентов страницы](../../atl/reference/atl-active-server-page-component-wizard.md).

## <a name="see-also"></a>См. также

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
[Добавление нового интерфейса в проект ATL](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)   
[Добавление точек подключения к объекту](../../atl/adding-connection-points-to-an-object.md)   
[Добавление метода](../../ide/adding-a-method-visual-cpp.md)   
[Класс MFC](../../mfc/reference/adding-an-mfc-class.md)   
[Добавление универсального класса C++](../../ide/adding-a-generic-cpp-class.md)

