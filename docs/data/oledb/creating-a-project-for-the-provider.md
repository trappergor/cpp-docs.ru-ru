---
title: Создание проекта для поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, creating
- OLE DB providers, projects
- projects [C++], creating
ms.assetid: 076a75de-1d4b-486a-bcf8-9c0f6b049fa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 86f85b95b4b45624a778bc183cabadda886d002d
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990091"
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