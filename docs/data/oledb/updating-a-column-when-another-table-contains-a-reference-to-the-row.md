---
title: Обновление столбца при наличии ссылки на строку другой таблицы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 17d260f522432a78729c9998c518398dfa41275a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102889"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Обновление столбца при наличии ссылки в другой таблице на данную строку
Некоторые поставщики можно обнаружить какие столбцы в изменения строки, однако многие поставщики невозможно. В результате обновление столбца может привести к ошибке, при наличии ссылки на строку, которую вы пытаетесь обновить. Чтобы решить эту проблему, создайте отдельный метод доступа, содержащий только те столбцы, которые вы хотите изменить. Передать число методов доступа к `SetData`.  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)