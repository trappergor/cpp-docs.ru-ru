---
title: "CWinApp и мастер приложений MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CWinApp
dev_langs: C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1e1eb73bf0b4a3eb91be63f3953959fa67e0737
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp и мастер приложений MFC
Когда она создает схему приложения, мастер приложений MFC объявляет приложения класс, производный от [CWinApp](../mfc/reference/cwinapp-class.md). Мастер приложений MFC также создает файл реализации, который содержит следующие элементы:  
  
-   Сопоставление сообщений для класса приложения.  
  
-   Конструктор пустым классом.  
  
-   Переменная, которая объявляет один и только объект класса.  
  
-   Стандартная реализация вашей `InitInstance` функции-члена.  
  
 Класс приложения помещается в заголовок проекта и основные исходные файлы. Имена класса и файлы, созданные основаны на имени проекта, укажите в мастере приложений MFC. Самый простой способ просмотреть код для этих классов является через [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Стандартные реализации и указано в схеме не подходит для многих целей, но при необходимости их можно изменить. Интересно этих реализаций `InitInstance` функции-члена. Как правило, будет добавлен код базовой реализации `InitInstance`.  
  
## <a name="see-also"></a>См. также  
 [CWinApp: Класс приложений](../mfc/cwinapp-the-application-class.md)   
 [Переопределяемые CWinApp функции-члены](../mfc/overridable-cwinapp-member-functions.md)   
 [Специальные службы CWinApp](../mfc/special-cwinapp-services.md)

