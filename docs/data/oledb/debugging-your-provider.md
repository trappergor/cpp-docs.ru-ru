---
title: Отладка поставщика
ms.date: 10/29/2018
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
ms.openlocfilehash: 15e9df58d4b31a8e69999c9ec7c22af158d08b38
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265091"
---
# <a name="debugging-your-provider"></a>Отладка поставщика

Существует два способа отладки поставщика:

- Поскольку поставщики создаются в процессе, можно создать определенный код потребителя, обычно используя шаблоны потребителей OLE DB и перейти к поставщику.

- Можно использовать различные служебные программы, входящие в состав Visual C++.

## <a name="to-use-debugging"></a>Чтобы использовать средство отладки

1. Откройте проект поставщика.

1. На **проекты** меню, щелкните **свойства**.

1. В **страницы свойств** диалоговом окне щелкните **Отладка** вкладки.

1. Выберите параметры, как требуется, нажмите кнопку **ОК**.

1. Установите точки останова и выполните отладку обычным образом.

## <a name="see-also"></a>См. также

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)