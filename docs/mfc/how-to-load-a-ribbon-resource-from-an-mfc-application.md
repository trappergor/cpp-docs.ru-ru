---
title: 'Как: загрузка ресурса ленты из приложения MFC | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b014e1725ae6c5043c051242a74e29338c3ef2d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Практическое руководство. Загрузка ресурса ленты из приложения MFC
Чтобы использовать ресурс ленты в приложении, измените приложения для загрузите ресурс ленты.  
  
### <a name="to-load-a-ribbon-resource"></a>Чтобы загрузить ресурс ленты  
  
1.  Объявите `Ribbon Control` объекта в `CMainFrame` класса.  
  
 ```  
    CMFCRibbonBar m_wndRibbonBar;   
 ```  
  
2.  В `CMainFrame::OnCreate`, создать и инициализировать элемент управления на ленте.  
  
 ```  
    if (!m_wndRibbonBar.Create (this))  
 {  
    return -1;  
 }  
 
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
 {  
    return -1;  
 }  
 ```  
  
## <a name="see-also"></a>См. также  
 [Конструктор ленты (MFC)](../mfc/ribbon-designer-mfc.md)

