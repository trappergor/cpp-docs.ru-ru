---
title: Отладка поставщика
ms.date: 10/29/2018
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
ms.openlocfilehash: f80ce5dc82dd2baeefe3410a488a5fefda0e9bf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211098"
---
# <a name="debugging-your-provider"></a>Отладка поставщика

Существует два способа отладки поставщика:

- Так как поставщики создаются в процессе, можно создать некоторый код потребителя, используя шаблоны OLE DB потребителей, и в обычном режиме перейти к поставщику.

- Вы можете использовать различные служебные программы, которые C++входят в состав Visual.

## <a name="to-use-debugging"></a>Использование отладки

1. Откройте проект поставщика.

1. В меню **проекты** выберите пункт **свойства**.

1. В диалоговом окне **страницы свойств** перейдите на вкладку **Отладка** .

1. Выберите необходимые параметры, нажмите кнопку **ОК**.

1. Задайте точки останова, а затем выполните отладку обычным образом.

## <a name="see-also"></a>См. также раздел

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
