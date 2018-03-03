---
title: "Параметры для CStatusBarCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 814c12b13333d589cb568c5c637f0fa34956847e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-cstatusbarctrl"></a>Параметры для CStatusBarCtrl
По умолчанию [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) — окно состояния в нижней части родительского окна, но можно указать `CCS_TOP` стиля, чтобы они появились в верхней части клиентской области родительского окна.  
  
 Можно указать **SBARS_SIZEGRIP** стиль можно включить захват для изменения размера в правом конце `CStatusBarCtrl` окно состояния. Захват для изменения размера аналогична границы для изменения размера; это прямоугольная область, которая пользователя можно щелкнуть и перетащить для изменения размера родительского окна.  
  
> [!NOTE]
>  При сочетании `CCS_TOP` и **SBARS_SIZEGRIP** стили, захвата для изменения размера не работает несмотря на то, что система отображает его в окне состояния.  
  
 Процедура окна для окна состояния автоматически задает начальный размер и положение окна элемента управления. Ширина одинаково как для клиентской области родительского окна. Высота основана на метрик шрифта, выбранного в данный момент в контексте устройства в окне состояния и ширину границ окна.  
  
 Процедура окна автоматически настраивается в соответствии с размером окна состояния всякий раз, когда он получает `WM_SIZE` сообщения. Как правило, когда размера родительского окна изменяется, отправляет родительского `WM_SIZE` сообщения в окне состояния.  
  
 Можно задать минимальную высоту области рисования в окне состояния путем вызова [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), указав минимальную высоту в пикселях. Область рисования не включает границы окна.  
  
 Ширина границы окна состояния извлечь, вызвав [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Эта функция-член содержит указатель на массив с тремя элементами, получающий ширины горизонтальной границы, вертикальной границы и границы между прямоугольниками.  
  
## <a name="see-also"></a>См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

