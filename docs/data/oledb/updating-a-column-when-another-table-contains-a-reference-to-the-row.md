---
title: Обновление столбца при наличии ссылки на строку другой таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7998897c80e392326213324804c1809656e051f3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071827"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Обновление столбца при наличии ссылки в другой таблице на данную строку

Некоторые поставщики можно обнаружить какие столбцы в изменении в строке, но многие поставщики не может. В результате обновление столбца может привести к ошибке при отсутствии ссылку на строку, которую вы пытаетесь обновить. Чтобы решить эту проблему, создайте отдельный метод доступа, содержащий только столбцы, которые вы хотите изменить. Передать число методов доступа к `SetData`.

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)