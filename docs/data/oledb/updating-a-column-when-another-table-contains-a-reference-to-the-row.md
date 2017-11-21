---
title: "Обновление столбца при наличии ссылки на строку другой таблицы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cac57f2f4a1175fa1d9f4009e10fd3d0fae2a3b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Обновление столбца при наличии ссылки в другой таблице на данную строку
Некоторые поставщики можно обнаружить какие столбцы в изменения строки, однако многие поставщики невозможно. В результате обновление столбца может привести к ошибке, при наличии ссылки на строку, которую вы пытаетесь обновить. Чтобы решить эту проблему, создайте отдельный метод доступа, содержащий только те столбцы, которые вы хотите изменить. Передать число методов доступа к `SetData`.  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)