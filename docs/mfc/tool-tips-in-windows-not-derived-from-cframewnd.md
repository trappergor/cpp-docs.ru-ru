---
title: Всплывающие подсказки в Windows, не являющиеся производными CFrameWnd | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34eb8f0b7394828782a3d0f9ed1ca44fb5731af6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>Всплывающие подсказки в Windows, не являющиеся производными CFrameWnd
Это статье рассматриваются Включение всплывающих подсказок для элементов управления, содержащихся в окне, которое не является производным от [CFrameWnd](../mfc/reference/cframewnd-class.md). Статья [всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md) предоставляет сведения о всплывающих подсказок для элементов управления в `CFrameWnd`.  
  
 В этом семействе статье рассмотрены следующие темы.  
  
-   [Включение подсказок](../mfc/enabling-tool-tips.md)  
  
-   [Обработка уведомления TTN_NEEDTEXT для подсказок](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [TOOLTIPTEXT-структура](../mfc/tooltiptext-structure.md)  
  
 Автоматически отображаются всплывающие подсказки для кнопок и других элементов управления, содержащихся в родительское окно, производный от `CFrameWnd`. Это вызвано `CFrameWnd` имеет обработчик по умолчанию для [TTN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269) уведомления, который обрабатывает **TTN_NEEDTEXT** уведомления от средства совет элементы управления, связанные с элементами управления.  
  
 Тем не менее, этот обработчик по умолчанию не вызывается, когда **TTN_NEEDTEXT** из элемента управления всплывающей подсказки, связанный с элементом управления в окне, не отправляется уведомление `CFrameWnd`, такие как элемент управления диалоговым окном или представление формы. Таким образом, необходимо предоставить функцию обработчика событий для **TTN_NEEDTEXT** сообщение уведомления, чтобы отображать всплывающие подсказки для дочерних элементов управления.  
  
 Всплывающие подсказки по умолчанию, для windows с [CWnd::EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) отсутствует текст, связанный с ними. Чтобы получить текст подсказки для отображения, **TTN_NEEDTEXT** управления всплывающей подсказки родительское окно отправляется уведомление, непосредственно перед отображением подсказки. Если отсутствует обработчик для этого сообщения для назначения либо значение для **pszText** членом **TOOLTIPTEXT** структуры, не будет не текст, отображаемый для всплывающей подсказки.  
  
## <a name="see-also"></a>См. также  
 [Подсказки](../mfc/tool-tips.md)

