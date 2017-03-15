---
title: "CReBar и CReBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CReBar"
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar - класс, или CReBarCtrl"
  - "GetReBarCtrl - класс"
  - "Элементы управления главной панели, CReBarCtrl - класс"
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReBar и CReBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC предоставляет 2 класса для создания основных панели: [CReBar](../mfc/reference/crebar-class.md) и [CReBarCtrl](../mfc/reference/crebarctrl-class.md) \(API, создания общего элемента управления Windows\).  **CReBar** предоставляет всю функциональность общего элемента управления главной панели, и он обрабатывает большую часть необходимых параметров и структур общего элемента управления автоматически.  
  
 `CReBarCtrl` класс\-оболочка для элемента управления "Главная панель" Win32, и поэтому может существенно упростить для реализации, если не планируется интеграции главной панели архитектуры в MFC.  Если планируется использовать `CReBarCtrl` и интегрировать главной панели в архитектуру MFC, необходимо соблюдать осторожность дополнительный для связи манипуляции элемента управления "Главная панель" с MFC.  Это сообщение не сложно; однако дополнительную работу, не нужен при использовании метода **CReBar**.  
  
 Visual C\+\+ 2 C предоставляет два способа использования общего элемента управления главной панели.  
  
-   Создайте главную панель с помощью **CReBar**, а затем вызвать [CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md), чтобы получить доступ к функциям элемента `CReBarCtrl`.  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl` встроенный функцию\-член, что указатель **this** объекта главной панели.  Это означает, что во время выполнения, вызов функции отсутствует нагрузку.  
  
-   Создание главной панели конструктора с помощью [CReBarCtrl](../mfc/reference/crebarctrl-class.md).  
  
 Любой метод выдаст доступ к функциям элемента элемента управления "Главная панель".  При вызове `CReBar::GetReBarCtrl`, оно возвращает ссылку на объект `CReBarCtrl` таким образом можно использовать любой набор функции\-члены.  В разделе [CReBar](../mfc/reference/crebar-class.md) сведения о построении и создание главной панели с помощью **CReBar**.  
  
## См. также  
 [Использование CReBarCtrl](../Topic/Using%20CReBarCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)