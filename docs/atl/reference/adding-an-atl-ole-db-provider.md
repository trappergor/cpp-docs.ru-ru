---
title: Добавление поставщика OLE DB в ATL
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB, adding ATL OLE DB provider to projects
- ATL projects, adding ATL OLE DB providers
- ATL OLE DB providers
ms.assetid: 26fba1e3-880f-4bc6-90e5-2096a48a3a6c
ms.openlocfilehash: 36c07da6249a106836433e127f95258d4ed5b509
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65706943"
---
# <a name="adding-an-atl-ole-db-provider"></a>Добавление поставщика OLE DB в ATL

::: moniker range="vs-2019"

Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=vs-2017"

Этот мастер используется для добавления поставщика OLE DB в ATL в проект. Поставщик OLE DB в ATL состоит из источника данных, сеанса, команды и классов набора строк. Проект для его реализации создается как COM-приложение ATL.

## <a name="to-add-an-atl-ole-db-provider-to-your-project"></a>Добавление поставщика OLE DB в ATL в проект

1. В разделе **Представление классов** щелкните проект правой кнопкой мыши. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. В папке **Visual C++** дважды щелкните значок **поставщика OLE DB в ATL** или выберите его и нажмите кнопку **Открыть**.

   Откроется мастер поставщика OLE DB в ATL.

1. Задайте параметры, как описано в статье [ATL OLE DB Provider Wizard](../../atl/reference/atl-ole-db-provider-wizard.md) (Мастер поставщика OLE DB в ATL).

1. Нажмите кнопку **Готово**, чтобы закрыть мастер, который вставит только что созданный код поставщика OLE DB в проект.

::: moniker-end

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)
