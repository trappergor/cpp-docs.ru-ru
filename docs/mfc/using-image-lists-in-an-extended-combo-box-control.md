---
title: Использование списков изображений в элементе управления "Расширенное поле со списком"
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 6e4d983d53e49fc8d9c80c206f1a23078eb82f61
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266995"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Использование списков изображений в элементе управления "Расширенное поле со списком"

Основной функцией вид Расширенное поле со списком полей является возможность связи изображений из списка изображений с отдельными элементами в поле со списком. Каждый элемент может отображать три различных изображений: один для выбранного состояния, по одному для его невыбранные состояние, а третий для наложения изображения.

Следующая процедура связывает списка изображений с элементом управления поле Расширенное поле со списком:

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Для связывания списка изображений с элементом управления поле Расширенное поле со списком

1. Создать список изображений (или использование существующего объекта списка изображений), с помощью [CImageList](../mfc/reference/cimagelist-class.md) конструктор и хранения результирующий указатель.

1. Инициализируйте новый объект списка образа путем вызова [CImageList::Create](../mfc/reference/cimagelist-class.md#create). Следующий код является примером этого вызова.

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. Добавить необязательный образы для каждого возможного состояния: выбранной или невыбранным и наложение. Следующий код добавляет три стандартных образов.

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. Связать список изображений с элементом управления с помощью вызова [CComboBoxEx::SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist).

После того как список изображений сопоставится с элементом управления, можно отдельно указать изображения, которые каждый элемент будет использовать для трех состояний. Дополнительные сведения см. в разделе [установка изображений для отдельного элемента](../mfc/setting-the-images-for-an-individual-item.md).

## <a name="see-also"></a>См. также

[Использование CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
