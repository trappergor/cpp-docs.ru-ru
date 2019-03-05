---
title: Добавление потребителя ATL OLE DB
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: d93bf715f8fd8a03c75b1d1bf2e44f12c1d1b9c0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277655"
---
# <a name="adding-an-atl-ole-db-consumer"></a>Добавление потребителя ATL OLE DB

Этот мастер используется для добавления потребителя ATL OLE DB в проект. Потребителя ATL OLE DB состоит из OLE DB для метода доступа класса и привязки данных для доступа к источнику данных. Проект необходимо создать как ATL COM-приложение или как приложение MFC или Win32, который включает в себя поддержку ATL (который автоматически добавляет Мастер потребителя ATL OLE DB).

> [!NOTE]
> Потребитель OLE DB можно добавить в проект MFC. В противном случае мастер потребителя ATL OLE DB добавляет необходимую поддержку COM в проект. Предполагается, что при создании проекта MFC был установлен **элементы управления ActiveX** флажок (в **дополнительные функции** страницы мастера приложений MFC проекта), который установлен по умолчанию. При выборе этого параметра гарантирует, что приложение вызывает `CoInitialize` и `CoUninitialize`. Если вы не выбрали **элементы управления ActiveX** при создании проекта MFC, необходимо вызвать `CoInitialize` и `CoUninitialize` в основном коде.

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Добавление потребителя ATL OLE DB в проект

1. В **представление классов**, щелкните правой кнопкой мыши проект. В контекстном меню, щелкните **добавить** и нажмите кнопку **Добавление класса**.

1. В папке Visual C++, дважды щелкните **потребителя ATL OLE DB** значок или выберите его и нажмите кнопку **откройте**.

   Откроется Мастер потребителя ATL OLE DB.

1. Задайте параметры, как описано в разделе [Мастер потребителя ATL OLE DB](../../atl/reference/atl-ole-db-consumer-wizard.md).

1. Нажмите кнопку **Готово** чтобы закрыть мастер. Вновь созданный код потребителя OLE DB будет вставлен в проекте.

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)
