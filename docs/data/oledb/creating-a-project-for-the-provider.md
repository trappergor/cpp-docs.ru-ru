---
title: Создание проекта для поставщика
ms.date: 10/22/2018
helpviewer_keywords:
- ATL projects, creating
- OLE DB providers, projects
- projects [C++], creating
ms.assetid: 076a75de-1d4b-486a-bcf8-9c0f6b049fa2
ms.openlocfilehash: dc085b1f663369033947ed2a5577f334dd79c0aa
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030742"
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