---
title: "Как: загрузка ресурса ленты из приложения MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a943f82fc9b438a74af3673e0210612183304c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

