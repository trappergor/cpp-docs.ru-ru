---
title: Обновление столбца при наличии ссылки на строку другой таблицы
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 46de5f54a3ec6525f779a6b55a700429a2a84fef
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039219"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Обновление столбца при наличии ссылки в другой таблице на данную строку

Некоторые поставщики можно обнаружить какие столбцы в изменении в строке, но многие поставщики не может. В результате обновление столбца может привести к ошибке при отсутствии ссылку на строку, которую вы пытаетесь обновить. Чтобы решить эту проблему, создайте отдельный метод доступа, содержащий только столбцы, которые вы хотите изменить. Передать число методов доступа к `SetData`.

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)