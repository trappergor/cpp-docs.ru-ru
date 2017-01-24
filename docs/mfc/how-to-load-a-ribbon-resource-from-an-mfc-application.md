---
title: "Практическое руководство. Загрузка ресурса ленты из приложения MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ресурс ленты, загрузка"
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Загрузка ресурса ленты из приложения MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для использования ресурсов ленты в приложении измените приложения загрузить ресурс ленты.  
  
### Загрузить ресурс ленты  
  
1.  Объявите объект `Ribbon Control` в классе `CMainFrame`.  
  
    ```  
    CMFCRibbonBar m_wndRibbonBar;   
    ```  
  
2.  В `CMainFrame::OnCreate` создайте и инициализируйте элемента управления на ленте.  
  
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
  
## См. также  
 [Конструктор лент \(MFC\)](../mfc/ribbon-designer-mfc.md)