---
title: CWinApp и мастер приложений MFC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59fcd3f00fb8998cf90c88d574b9d22051cb4305
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687788"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp и мастер приложений MFC
Когда он создает скелет приложения, мастер приложений MFC объявляет класс приложения, производный от [CWinApp](../mfc/reference/cwinapp-class.md). Мастер приложений MFC также создает файл реализации, который содержит следующие элементы:  
  
-   Сопоставление сообщений для класса приложения.  
  
-   Конструктор пустого класса.  
  
-   Переменная, которая объявляет только объект класса.  
  
-   Стандартная реализация вашей `InitInstance` функция-член.  
  
 Класс приложения помещается в заголовок проекта и основных исходных файлов. Имена класса и файлы, созданные основаны на имени проекта, которое вы указали в мастере приложений MFC. Самым простым способом, чтобы просмотреть код для этих классов является через [представление классов](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Стандартные реализации и указано схему сообщений, подходит для многих целей, но при необходимости их можно изменить. Самым интересным из этих реализаций является `InitInstance` функция-член. Как правило, будет добавлен код для базовой реализации `InitInstance`.  
  
## <a name="see-also"></a>См. также  
 [CWinApp: Класс приложений](../mfc/cwinapp-the-application-class.md)   
 [Функции-члены CWinApp переопределяемый](../mfc/overridable-cwinapp-member-functions.md)   
 [Специальные службы CWinApp](../mfc/special-cwinapp-services.md)

