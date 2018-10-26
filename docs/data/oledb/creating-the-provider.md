---
title: Создание поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 10/15/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 230620a2375ac5aa822e55496d1f26751ee6f7b3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055350"
---
# <a name="creating-the-provider"></a>Создание поставщика

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>Для создания поставщика OLE DB с помощью мастера поставщика ATL OLE DB

1. Щелкните правой кнопкой мыши проект.

1. В контекстном меню, щелкните **добавить**, а затем нажмите кнопку **Добавление класса**.

1. В **Добавление класса** диалогового **установленные** > **Visual C++** > **ATL**, выберите **Поставщик OLEDB библиотеки ATL** значок, а затем щелкните **откройте**.

1. В **мастер поставщика ATL OLE DB**, введите короткое имя поставщика в **короткое имя** поле. Короткое имя используется в следующих разделах *Custom*, но вы можете использовать другое имя. Остальные поля заполняются в соответствии с введенное имя.

1. При необходимости измените имя поля. Помимо имен объектов и файлов вы можете изменить следующие:

   - **Компонентный класс**: имя, которое использует COM для создания поставщика.

   - **Идентификатор progID**: программный идентификатор, который представляет собой текстовую строку, которая может использоваться вместо GUID.

   - **Версия**: используется с ProgID и Coclass для создания программного идентификатора, зависящие от версии.

1. Нажмите кнопку **Готово**.

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)
