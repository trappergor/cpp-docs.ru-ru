---
title: Создание проекта для поставщика
ms.date: 10/22/2018
helpviewer_keywords:
- ATL projects, creating
- OLE DB providers, projects
- projects [C++], creating
ms.assetid: 076a75de-1d4b-486a-bcf8-9c0f6b049fa2
ms.openlocfilehash: f63b09d47dd8f3ebe8750275bb005be89ca8fde8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677114"
---
# <a name="creating-a-project-for-the-provider"></a>Создание проекта для поставщика

## <a name="to-create-a-project-in-which-the-ole-db-provider-will-reside"></a>Чтобы создать проект, в которой будет находиться поставщик OLE DB

1. В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.

   Откроется диалоговое окно **Новый проект** .

1. В **типы проектов** панели щелкните **установленные** > **Visual C++** > **MFC/ATL** папки. В **шаблоны** панели щелкните **проекта ATL**.

    > [!NOTE]
    > В предыдущих версиях Visual Studio, найдите типа проекта в разделе **установленные** > **шаблоны** > **Visual C++**  >  **ATL**.

1. В **имя** введите имя для проекта и нажмите кнопку **ОК**.

   **Мастер проектов ATL** отображается.

1. В **мастер проектов ATL**, выберите **библиотеки динамической компоновки (DLL)** для **тип приложения**.

1. Нажмите кнопку **Готово**.

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)