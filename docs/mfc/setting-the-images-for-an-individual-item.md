---
title: "Установка изображений для отдельного элемента | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "изображения [C++], элементы поля со списком"
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Установка изображений для отдельного элемента
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Различные типы изображений, используемых дополнительным элементом поля со списком определяются значениями в `iImage`, **iSelectedImage** и **iOverlay** членов структуры [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746).  Каждое значение индекса образа в связанном списке изображений элемента управления.  По умолчанию эти члены задано значение 0, что элемент управления не отображаться. изображение элемента.  Если требуется использовать отображает для конкретного элемента, можно изменять структуру соответствующим образом при вставке элемента поля со списком или путем изменения существующего элемента поля со списком.  
  
## Параметр изображение для нового элемента  
 При вставке новый элемент, необходимо инициализировать `iImage`, **iSelectedImage** и **iOverlay** элементы структуры с правильными значениями и затем вставьте элемент с вызовом метода [CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md).  
  
 Следующий пример вставляет новый расширенный элемент поля со списком \(`cbi`\) в расширенных элементов управления " Поле со списком \(`m_comboEx`\), указав индексы для всех 3 состояний образа.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/CPP/setting-the-images-for-an-individual-item_1.cpp)]  
  
## Параметр изображение для существующего элемента  
 Если изменить существующий элемент, необходимо работать с членом **mask** структуры **COMBOBOXEXITEM**.  
  
#### Изменить существующий элемент для использования изображений  
  
1.  Объявите структуру **COMBOBOXEXITEM** и задайте элемент данных **mask** значения необходимо настроить в изменения.  
  
2.  С помощью этой структуры, вызывать в [CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md).  
  
3.  Измените **mask**, `iImage` и члены **iSelectedImage** вновь возвращенной структуры, используя соответствующие значения.  
  
4.  Вызывать в [CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md), передав измененную структуру.  
  
 Следующий пример демонстрирует эту процедуру с обменивать выбранные и не выбран образы удлиненного третьего элемента поля со списком.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/CPP/setting-the-images-for-an-individual-item_2.cpp)]  
  
## См. также  
 [Использование CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Элементы управления](../mfc/controls-mfc.md)