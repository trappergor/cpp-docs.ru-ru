---
title: Обработчики для команд и уведомлений элементов управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e6492c6ecc4c21c5c978ad031fed7182f2acee4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347237"
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
