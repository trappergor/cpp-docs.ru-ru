---
title: Древовидная уведомляющих сообщений элемента управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92035d3f1a20a0fd9cc0c7b95d7238ef014033da
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950971"
---
# <a name="tree-control-notification-messages"></a>Уведомляющие сообщения древовидного элемента управления
Структура дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет следующие сообщения уведомления в виде сообщения WM_NOTIFY:  
  
|Сообщение уведомления|Описание:|  
|--------------------------|-----------------|  
|TVN_BEGINDRAG|Сигнализирует о начале операции перетаскивания и вставки|  
|TVN_BEGINLABELEDIT|Сигнализирует о начале изменения метки на месте|  
|TVN_BEGINRDRAG|Сигнализирует о начале операции перетаскивания и вставки, с помощью правой кнопки мыши|  
|TVN_DELETEITEM|Сообщает удаления конкретного элемента|  
|TVN_ENDLABELEDIT|Сигнализирует о завершении редактирования метки|  
|TVN_GETDISPINFO|Запрашивает информацию, что дерево требуется для отображения элемента|  
|TVN_ITEMEXPANDED|Сообщает, что родительский элемент списка дочерних элементов был развернут или свернут|  
|TVN_ITEMEXPANDING|Показывает, будет разворачивать и сворачивать с родительским элементом списка дочерних элементов|  
|TVN_KEYDOWN|Указывает события клавиатуры|  
|TVN_SELCHANGED|Указывает, что выбор был перенесен с одного элемента на другой|  
|TVN_SELCHANGING|Показывает, выбор перенесен с одного элемента на другой|  
|TVN_SETDISPINFO|Уведомление для обновления сведений, поддерживаемых для элемента|  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

