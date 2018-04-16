---
title: Использование редактора диалоговых окон для добавления элементов управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controls [MFC], adding to dialog boxes
- Dialog editor, creating controls
- common controls [MFC], adding
ms.assetid: d3f9f994-7e54-4656-a545-42c204557c36
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 64ed32054c05ca012bc230ede47fa08e4d24595d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-dialog-editor-to-add-controls"></a>Использование редактора диалоговых окон для добавления элементов управления
При создании ресурса шаблона диалогового окна с [редактор диалоговых окон](../windows/dialog-editor.md), перетащите элементы управления из палитры элементов управления и перетащить их в диалоговом окне. Это добавляет спецификации для данного типа элемента управления ресурса шаблона диалогового окна. При построении объекта диалогового окна и вызовите его **создать** или `DoModal` функция-член, платформа создает элемент управления Windows и помещает его в диалоговом окне на экране.  
  
 Вместо этого можно [вручную создавать элементы управления](../mfc/adding-controls-by-hand.md) Если требуется. Это больше работы.  
  
## <a name="see-also"></a>См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)

