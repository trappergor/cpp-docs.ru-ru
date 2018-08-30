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
ms.openlocfilehash: 0a716119acc857419dcf128c39ab2c20921cd2d4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211395"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp и мастер приложений MFC
Когда он создает скелет приложения, мастер приложений MFC объявляет класс приложения, производный от [CWinApp](../mfc/reference/cwinapp-class.md). Мастер приложений MFC также создает файл реализации, который содержит следующие элементы:  
  
-   Сопоставление сообщений для класса приложения.  
  
-   Конструктор пустого класса.  
  
-   Переменная, которая объявляет только объект класса.  
  
-   Стандартная реализация вашей `InitInstance` функция-член.  
  
 Класс приложения помещается в заголовок проекта и основных исходных файлов. Имена класса и файлы, созданные основаны на имени проекта, которое вы указали в мастере приложений MFC. Самым простым способом, чтобы просмотреть код для этих классов является через [представление классов](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Стандартные реализации и указано схему сообщений, подходит для многих целей, но при необходимости их можно изменить. Самым интересным из этих реализаций является `InitInstance` функция-член. Как правило, будет добавлен код для базовой реализации `InitInstance`.  
  
## <a name="see-also"></a>См. также  
 [CWinApp: Класс приложений](../mfc/cwinapp-the-application-class.md)   
 [Функции-члены CWinApp переопределяемый](../mfc/overridable-cwinapp-member-functions.md)   
 [Специальные службы CWinApp](../mfc/special-cwinapp-services.md)

