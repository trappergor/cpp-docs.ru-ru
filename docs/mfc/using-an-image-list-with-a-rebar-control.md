---
title: Использование списка изображений с элементом управления главной панели | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f902cb24d5cd8525a99f58fc5feeac416138148
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Использование списка изображений с элементом управления главной панели
Каждой зоны главной панели могут содержать, помимо прочего, изображение из списка связанных изображений. В следующей процедуре подробно шаги, необходимые для отображения изображения в области главной панели.  
  
### <a name="to-display-images-in-a-rebar-band"></a>Для отображения изображений в области главной панели  
  
1.  Присоединить объект управления главной панели списка изображений путем вызова [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), указателю на существующий список изображений.  
  
2.  Изменить **REBARBANDINFO** структуры, чтобы назначить изображения для области главной панели:  
  
    -   Задать **fMask** члена **RBBIM_IMAGE**, используя оператор побитового или для включения дополнительных флагов при необходимости.  
  
    -   Задать `iImage` элемент списка индекс изображения изображения для отображения.  
  
3.  Инициализируйте все оставшиеся элементы данных, такие как размер, текст и дескриптор автономной дочернего окна, указав необходимые сведения.  
  
4.  Вставить новый диапазон (с изображением) с помощью вызова [CReBarCtrl::InsertBand](../mfc/reference/crebarctrl-class.md#insertband), передав **REBARBANDINFO** структуры.  
  
 В следующем примере предполагается, что существующего объекта списка изображений с двумя образами был присоединен к объекту управления главной панели (`m_wndReBar`). Новый диапазон на главной панели (определяется `rbi`), содержащая первое изображение, добавлена с помощью вызова `InsertBand`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Использование CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

