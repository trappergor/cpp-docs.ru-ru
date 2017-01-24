---
title: "Использование списков изображений в элементе управления &quot;Расширенное поле со списком&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "расширенные поля со списком, изображения"
  - "списки изображений [C++], поля со списком"
  - "изображения [C++], элементы поля со списком"
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование списков изображений в элементе управления &quot;Расширенное поле со списком&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Основной функции расширенных элементов управления " Поле со списком возможность сопоставлять изображения из списка изображений с отдельными элементами в элементе управления " Поле со списком.  Каждый элемент может отображать 3 различных способа: одно для своего выбранного состояния, один для его nonselected состояния и третий для образа перекрытия.  
  
 В следующей процедуре связывает список изображений расширенный элемент управления " Поле со списком:  
  
### Связывание списка изображений расширенный элемент управления " Поле со списком  
  
1.  Создайте новый список изображений \(или использовать существующий объект списка изображений\), используя конструктор [CImageList](../Topic/CImageList%20Class.md) и хранения результирующий указатель.  
  
2.  Инициализируйте новый объект списка изображений с помощью метода [CImageList::Create](../Topic/CImageList::Create.md).  Следующий код является примером этого вызова.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  Добавьте дополнительные образы для каждого возможного состояния: выбранный или nonselected и наложение.  Следующий код добавляет 3 предопределенных образа.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  Связывание списка изображений с элементом управления, вызвав метод [CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md).  
  
 После списка изображений связанный с элементом управления, можно задать способ по отдельности каждый элемент будет использовать для 3 состояний.  Дополнительные сведения см. в разделе [Параметр образы для отдельного элемента](../mfc/setting-the-images-for-an-individual-item.md).  
  
## См. также  
 [Использование CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Элементы управления](../mfc/controls-mfc.md)