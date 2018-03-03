---
title: "Элементы списков и списки изображений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 525d8353c308796d70f974fa56cde3aa76c12142
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="list-items-and-image-lists"></a>Элементы списков и списки изображений
«Элемент» в элементе управления списком ([CListCtrl](../mfc/reference/clistctrl-class.md)) состоит из значка, метку и, возможно, другие сведения (в «подэлементы»).  
  
 Значки для элементов управления списка, содержащиеся в списках изображений. Один список изображений содержит полноразмерное значков, используемых в виде значков. Список второй, необязательный, образ содержит уменьшенных версий же значки для использования в других представлениях элемента управления. Третий необязательный список содержит изображения «состояние», например, флажки для отображения перед мелких значков в определенных режимах. Четвертый необязательный список содержит изображения, которые отображаются в отдельных заголовок элементов управления "список".  
  
> [!NOTE]
>  Если при создании элемента управления представления списка `LVS_SHAREIMAGELISTS` стиля, вы несете ответственность за уничтожение списков изображений, когда они больше не используется. Указывайте этот стиль, если назначить тот же образ списки для нескольких элементов управления представления списка; в противном случае более одного элемента управления может попытаться удалить один список изображений.  
  
 Дополнительные сведения об элементах списка см. в разделе [списки изображений представление списка](http://msdn.microsoft.com/library/windows/desktop/bb774736) и [элементы и подэлементы](http://msdn.microsoft.com/library/windows/desktop/bb774736) в Windows SDK. См. также класс [CImageList](../mfc/reference/cimagelist-class.md) в *Справочник по библиотеке MFC* и [использование CImageList](../mfc/using-cimagelist.md) в этот сборник статей.  
  
 Чтобы создать элемент управления списка, необходимо ввести списков изображений для использования при вставке новых элементов в списке. Ниже приведен пример этой процедуры, где `m_pImagelist` — указатель типа `CImageList` и `m_listctrl` — `CListCtrl` члена данных.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]  
  
 Тем не менее если не планируется отображение значков в представлении списка или управления "список", нет необходимости списков изображений.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

