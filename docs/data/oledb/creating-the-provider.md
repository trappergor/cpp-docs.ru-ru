---
title: Создание поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 1063b3418df0c9dd45848ea71cdd7717c2dd1427
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48859592"
---
# <a name="creating-the-provider"></a>Создание поставщика

#### <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>Для создания поставщика OLE DB с помощью мастера поставщика ATL OLE DB

1. Щелкните правой кнопкой мыши проект.

1. В контекстном меню, щелкните **добавить**, а затем нажмите кнопку **Добавление класса**.

1. В **Добавление класса** выберите **поставщика ATL OLE DB** значок, а затем щелкните **откройте**.

1. В мастере поставщика OLE DB ATL введите короткое имя поставщика в **короткое имя** поле. Короткое имя «MyProvider» используется в следующих разделах, но можно использовать другое имя. Остальные поля заполняются в соответствии с введенное имя.

1. При необходимости измените имя поля. Помимо имен объектов и файлов вы можете изменить следующие:

   - **Компонентный класс**: имя, которое использует COM для создания поставщика.

   - **Идентификатор progID**: программный идентификатор, который представляет собой текстовую строку, которая может использоваться вместо GUID.

   - **Версия**: используется с ProgID и coclass для создания программного идентификатора, зависящие от версии.

1. Нажмите кнопку **Готово**.

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)
