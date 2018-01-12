---
title: "Обработчики для команд и уведомлений элементов управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 748bdd1a2ce6b94a2c935df94de68767ee36875e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-commands-and-control-notifications"></a>Обработчики для команд и уведомлений элементов управления
Существуют обработчики не по умолчанию для команды или сообщения уведомления элемента управления. Таким образом вы связаны только по соглашению в именовании обработчиков эти категории сообщений. При сопоставлении обработчика уведомлений команда или элемент управления, свойства windows предлагает имя, основанное на код ID или уведомление элемента управления. Можно принять предложенное имя, изменить его или заменить его.  
  
 Соглашение о предполагает, что имена обработчиков в обе категории для объектов пользовательского интерфейса, которые они представляют. Таким образом может называться обработчик для команды перехода в меню "Правка"  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]  
  
 Так как команда Вырезать так часто реализуется в приложениях, платформа есть стандартные идентификатор команды для команды "Вырезать" как **ID_EDIT_CUT**. Список всех стандартные идентификаторы команд см. в файле AFXRES. З. Дополнительные сведения см. в разделе [стандартные команды](../mfc/standard-commands.md).  
  
 Кроме того, соглашение о предлагает обработчик **BN_CLICKED** может называться сообщение уведомления с помощью кнопки с надписью «Моя кнопка»  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]  
  
 Эта команда может назначить Идентификатором `IDC_MY_BUTTON` , так как она эквивалентна объект пользовательского интерфейса приложения.  
  
 Обе категории сообщений не принимают аргументов и не возвращает значение.  
  
## <a name="see-also"></a>См. также  
 [Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)
