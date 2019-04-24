---
title: Отладка поставщика
ms.date: 10/29/2018
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
ms.openlocfilehash: 21d4cb455413c3f7cbcbed02cdd4c364a469426d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033883"
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