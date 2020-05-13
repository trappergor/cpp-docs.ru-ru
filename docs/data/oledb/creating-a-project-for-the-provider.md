---
title: Создание проекта для поставщика
ms.date: 10/22/2018
helpviewer_keywords:
- ATL projects, creating
- OLE DB providers, projects
- projects [C++], creating
ms.assetid: 076a75de-1d4b-486a-bcf8-9c0f6b049fa2
ms.openlocfilehash: f2ff42ba8a2e908f672db7e96fc9f24f51a1fd9b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211410"
---
# <a name="creating-a-project-for-the-provider"></a>Создание проекта для поставщика

## <a name="to-create-a-project-in-which-the-ole-db-provider-will-reside"></a>Создание проекта, в котором будет располагаться поставщик OLE DB

1. В меню **Файл** выберите команду **Создать**, а затем — **Проект**.

   Откроется диалоговое окно **Создание проекта** .

1. В области **типы проектов** выберите **установленный** > **Visual C++**  > **MFC/ATL** . В области **шаблоны** щелкните **проект ATL**.

    > [!NOTE]
    > В предыдущих версиях Visual Studio найдите тип проекта в разделе **установленные** **шаблоны** >  > **Visual C++**  > **ATL**.

1. В поле **имя** введите имя проекта и нажмите кнопку **ОК**.

   Откроется **Мастер проектов ATL** .

1. В **мастере проектов ATL**выберите **Библиотека динамической компоновки (DLL)** для **типа приложения**.

1. Нажмите кнопку **Готово**.

## <a name="see-also"></a>См. также раздел

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)
