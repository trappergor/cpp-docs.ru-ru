---
title: Параметры для CStatusBarCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1dde1f005e53aff7ebe505d1ce619bf5c94410f8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955460"
---
# <a name="settings-for-the-cstatusbarctrl"></a>Параметры для CStatusBarCtrl
По умолчанию [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) — окно состояния в нижней части родительского окна, но вы можете указать стиль CCS_TOP, чтобы они появились в верхней части клиентской области родительского окна.  
  
 Вы можете указать стиль SBARS_SIZEGRIP, чтобы включить захват для изменения размера в правом конце `CStatusBarCtrl` окно состояния. Захват для изменения размера аналогична границы для изменения размера; это прямоугольная область, которая пользователя можно щелкнуть и перетащить для изменения размера родительского окна.  
  
> [!NOTE]
>  При сочетании стили CCS_TOP и SBARS_SIZEGRIP захвата для изменения размера не работает, даже если система отображает его в окне состояния.  
  
 Процедура окна для окна состояния автоматически задает начальный размер и положение окна элемента управления. Ширина одинаково как для клиентской области родительского окна. Высота основана на метрик шрифта, выбранного в данный момент в контексте устройства в окне состояния и ширину границ окна.  
  
 Каждый раз, когда он получает сообщение WM_SIZE процедуру окна изменяется размер окна состояния. Как правило при изменении размера родительского окна, родительский отправляет сообщение WM_SIZE в окне состояния.  
  
 Можно задать минимальную высоту области рисования в окне состояния путем вызова [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), указав минимальную высоту в пикселях. Область рисования не включает границы окна.  
  
 Ширина границы окна состояния извлечь, вызвав [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Эта функция-член содержит указатель на массив с тремя элементами, получающий ширины горизонтальной границы, вертикальной границы и границы между прямоугольниками.  
  
## <a name="see-also"></a>См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

