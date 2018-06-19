---
title: Использование списков изображений в элементе управления поле Расширенное поле со списком | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c9a701871631fead48c22b1ffb2cbc3c386b960
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383349"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Использование списков изображений в элементе управления "Расширенное поле со списком"
Основных компонентов элементов управления Расширенное поле со списком имеет возможность связывания с отдельными элементами в поле со списком изображений из списка изображений. Каждый элемент будет отображаться три различные изображения: один для свое состояние выбора, один для его невыбранные состояние, а третий для наложения изображения.  
  
 Следующая процедура связывает списка изображений с расширенной списком:  
  
### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Для связывания списка изображений с элементом управления поле Расширенное поле со списком  
  
1.  Создать новый список изображений (или использование существующего объекта списка изображений), с помощью [CImageList](../mfc/reference/cimagelist-class.md) конструктор и сохранение результирующего указателя.  
  
2.  Инициализируйте новый объект списка изображений, вызвав [CImageList::Create](../mfc/reference/cimagelist-class.md#create). Следующий код является примером этого вызова.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  Добавить необязательный изображения для каждого возможного состояния: выбранный или невыбранным и наложения. Следующий код добавляет три стандартных образов.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  Связать список изображений с элементом управления с помощью вызова [CComboBoxEx::SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist).  
  
 После списка изображений с элементом управления, можно отдельно указать изображения, которые будут использовать каждый элемент для трех состояний. Дополнительные сведения см. в разделе [установка изображений для отдельного элемента](../mfc/setting-the-images-for-an-individual-item.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Элементы управления](../mfc/controls-mfc.md)

