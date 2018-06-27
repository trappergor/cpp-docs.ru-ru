---
title: Ситуации вызова обработчиков обновления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c033d33dd6b1e6c0ccd5bbdb4b6af6939521f592
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956178"
---
# <a name="when-update-handlers-are-called"></a>Ситуации вызова обработчиков обновления
Предположим, что пользователь нажимает кнопку мыши в меню «файл», создает сообщение WM_INITMENUPOPUP. Механизм обновления совокупности обновляет все элементы в меню файл перед раскрывающееся меню, поэтому пользователь может видеть его.  
  
 Чтобы сделать это, маршруты framework обновление команд для всех элементов меню вдоль стандартной маршрутизации команд всплывающего меню. Цели команды в маршруте предоставлена возможность обновить все пункты меню, соответствующие команды update с записью соответствующие схемы сообщений (формы `ON_UPDATE_COMMAND_UI`) и вызвав функцию «обработчика обновлений». Таким образом для меню с шестью элементами, шесть команды обновления будут отправлены. Если для элемента меню идентификатор команды существует обработчика обновлений, он называется для выполнения обновления. В противном случае платформа проверяет существование обработчик для этого идентификатора команды и включает или отключает пункт меню соответствующим образом.  
  
 Если не удается найти платформу `ON_UPDATE_COMMAND_UI` входа во время маршрутизации команд, он автоматически включает объект пользовательского интерфейса при наличии `ON_COMMAND` запись где-либо с тем же идентификатором команды. В противном случае он отключает объект пользовательского интерфейса. Таким образом Чтобы включить объект пользовательского интерфейса, предоставляете обработчик для команды, которую создает объект, или указать обработчика обновлений, для него. См. рисунок в разделе [объекты пользовательского интерфейса и идентификаторы команд](../mfc/user-interface-objects-and-command-ids.md).  
  
 Его можно отключить, отключение объекты пользовательского интерфейса по умолчанию. Дополнительные сведения см. в разделе [m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) член класса `CFrameWnd` в *Справочник по библиотеке MFC*.  
  
 Меню инициализации выполняется автоматически в структуре, возникающая, если приложение получает сообщение WM_INITMENUPOPUP. Во время цикла простоя выполнение платформой поиска по маршрутизация команд для обработчиков кнопку обновления в так же как и в случае меню.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)

