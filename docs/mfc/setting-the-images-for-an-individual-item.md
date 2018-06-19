---
title: Установка изображений для отдельного элемента | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7f3dbdf4d386e40802d74459dd2854035b5b7c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380605"
---
# <a name="setting-the-images-for-an-individual-item"></a>Установка изображений для отдельного элемента
Различные типы изображений, используемых элементом поле Расширенное поле со списком определяются по значениям в `iImage`, **iSelectedImage**, и **iOverlay** члены [COMBOBOXEXITEM ](http://msdn.microsoft.com/library/windows/desktop/bb775746) структуры. Каждое значение — это индекс образа в списке связанное изображение элемента управления. По умолчанию эти члены являются равным 0, вызывает элемент управления для отображения нет изображения для элемента. Если вы хотите использовать изображения для определенного элемента, можно изменить структуру соответственно, при вставке элемент поля со списком или путем изменения существующего элемента поле со списком.  
  
## <a name="setting-the-image-for-a-new-item"></a>Задание рисунка для элемента  
 При вставке нового элемента инициализировать `iImage`, **iSelectedImage**, и **iOverlay** члены с использованием соответствующих значений структур и затем вставить элемент, с помощью вызова [ CComboBoxEx::InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem).  
  
 Следующий пример вставляет новый элемент поля Расширенное поле со списком (`cbi`) в элемент управления поле "Расширенное поле со списком" (`m_comboEx`), предоставляющего индексы для всех трех изображения состояния:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]  
  
## <a name="setting-the-image-for-an-existing-item"></a>Задание изображения для существующего элемента  
 При добавлении или изменении существующего элемента, необходимые для работы с **маска** членом **COMBOBOXEXITEM** структуры.  
  
#### <a name="to-modify-an-existing-item-to-use-images"></a>Для изменения существующего элемента с помощью изображений  
  
1.  Объявите **COMBOBOXEXITEM** структуры и задать **маски** данные-члены значения вас интересуют изменения.  
  
2.  С помощью этой структуры вызвать [CComboBoxEx::GetItem](../mfc/reference/ccomboboxex-class.md#getitem).  
  
3.  Изменить **маска**, `iImage`, и **iSelectedImage** члены вновь возвращенной структуры, используя соответствующие значения.  
  
4.  Вызвать [CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem), передавая измененной структуры.  
  
 В следующем примере демонстрируется эту процедуру путем замены изображений выбранном и невыбранном третьего элемента поле Расширенное поле со списком:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Использование CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Элементы управления](../mfc/controls-mfc.md)

