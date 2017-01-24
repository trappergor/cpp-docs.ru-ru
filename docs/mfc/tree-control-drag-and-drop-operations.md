---
title: "Операции перетаскивания древовидного элемента управления | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl - класс, операции перетаскивания"
  - "перетаскивание, CTreeCtrl"
  - "элементы управления "дерево", операции перетаскивания"
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Операции перетаскивания древовидного элемента управления
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Элемент управления "Дерево" \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) отправляет уведомление при запуске пользователя для перетаскивания элементов.  Элемент управления отправляет сообщение уведомления [TVN\_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504), если пользователь начинает перетаскивание элемента удерживая нажатой левую кнопку мыши и сообщением уведомления [TVN\_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509), если пользователь начинает перетаскивание с правой кнопкой.  Можно предотвратить элемент управления "Дерево" из отправлять эти уведомления, используя элемент управления "Дерево" стиль **TVS\_DISABLEDRAGDROP**.  
  
 При получении изображение для отображения во время операции перетаскивания, вызвав функцию\-член [CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md).  Элемент управления "Дерево" создает при перетаскивании растровое изображение на основе метку, перетащенным элемента.  Затем элемент управления "Дерево" создает список изображений, добавляет растровое изображение в него и возвращает указатель на объект [CImageList](../Topic/CImageList%20Class.md).  
  
 Необходимо предоставить код, который фактически перетаскивает элемент.  Обычно это включает использование при перетаскивании возможности функций списка изображений и обрабатывать сообщения, отправляемые [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) и [WM\_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) \(или [WM\_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)\) после того, как начнется операция перетаскивания.  Дополнительные сведения о функции списка изображений см. в разделе [CImageList](../Topic/CImageList%20Class.md) в справочнике по MFC и [Списки изображений](http://msdn.microsoft.com/library/windows/desktop/bb761389) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Дополнительные сведения о при перетаскивании элемента управления "Дерево" см. в разделе [Перетаскивание элемента представления в виде дерева](http://msdn.microsoft.com/library/windows/desktop/bb760017), также в [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 Если элементы в элементе управления дерева быть целевыми объектами операции перетаскивания, необходимо знать, когда курсор мыши на элементе целевого объекта.  Можно узнать, вызвав функцию\-член [HitTest](../Topic/CTreeCtrl::HitTest.md).  Необходимо указать либо точку и целое число, или адрес структуры [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448), которая содержит текущие координаты курсора мыши.  Если функция возвращает целое число, или структура содержит флажок, указывающее местоположение курсора мыши относительно элемент управления дерева.  Если курсор над элементом в элементе управления дерева, структура содержит дескриптор элемента также.  
  
 Это свойство указывает, что элемент целевой объект операции перетаскивания, вызвав функцию\-член [SetItem](../Topic/CTreeCtrl::SetItem.md), чтобы задать состояние в `TVIS_DROPHILITED` значение.  Элемент, имеющий это состояние строится в стиле " для обозначения перетаскивания целевой объект.  
  
## См. также  
 [Использование CTreeCtrl](../Topic/Using%20CTreeCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)