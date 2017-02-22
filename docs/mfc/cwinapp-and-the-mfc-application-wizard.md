---
title: "CWinApp и мастер приложений MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "мастера приложений [C++], и CWinApp"
  - "CWinApp - класс, и мастер приложений MFC"
  - "MFC [C++], мастера"
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CWinApp и мастер приложений MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании схемы приложения мастер приложений MFC объявляет класс приложения, являющийся производным от [CWinApp](../mfc/reference/cwinapp-class.md).  Мастер приложений MFC также создает файл реализации, содержит следующие элементы:  
  
-   Схема сообщений для класса приложения.  
  
-   Конструктор пустой класс.  
  
-   Переменная, которая объявляет один и только один объект из класса.  
  
-   Стандартная реализация этого функции\-члена `InitInstance`.  
  
 Класс приложения помещается в заголовке проекта и файлы источника main.  Имена созданных классов и основываться на имени файла проекта указываются с помощью мастера приложений MFC.  Самый простой способ просмотра код этих классов с помощью [Представление классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Стандартные, реализации и схема сообщений адекватни для многих целей, но их можно изменять по мере необходимости.  Наиболее руководство интересным этих реализаций функцию\-член `InitInstance`.  Обычно необходимо добавить код в скелетной реализации `InitInstance`.  
  
## См. также  
 [CWinApp: класс приложений](../Topic/CWinApp:%20The%20Application%20Class.md)   
 [Переопределяемые функции\-члены CWinApp](../mfc/overridable-cwinapp-member-functions.md)   
 [Специальные службы CWinApp](../mfc/special-cwinapp-services.md)