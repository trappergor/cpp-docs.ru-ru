---
title: Обновление столбца при наличии ссылки на строку другой таблицы
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 2adca735558033aa9324f37b5a61385b5f48096c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519904"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Обновление столбца при наличии ссылки в другой таблице на данную строку

Некоторые поставщики можно обнаружить какие столбцы в изменении в строке, но многие поставщики не может. В результате обновление столбца может привести к ошибке при отсутствии ссылку на строку, которую вы пытаетесь обновить. Чтобы решить эту проблему, создайте отдельный метод доступа, содержащий только столбцы, которые вы хотите изменить. Передать число методов доступа к `SetData`.

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)