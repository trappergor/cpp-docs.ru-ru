---
title: Идентификаторы команд | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0dc27e39f6e2753b7b468e39c283d58c3e585d6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="command-ids"></a>Идентификаторы команд
Команда полностью описаны только его идентификатор команды (в кодировке **WM_COMMAND** сообщения). Этот идентификатор назначается объект пользовательского интерфейса, который формирует команды. Как правило были указаны идентификаторы функциональные возможности пользовательского интерфейса объекта, к которому они назначены.  
  
 Например, элемент "Очистить все" в меню "Правка" может быть назначен идентификатор таких как **ID_EDIT_CLEAR_ALL**. Библиотека классов есть стандартные некоторых кодов, особенно для команд, платформа обработки, такие как **ID_EDIT_CLEAR_ALL** или `ID_FILE_OPEN`. Вы создадите другие идентификаторы команд самостоятельно.  
  
 При создании собственных меню в Visual C++ редактор меню — хороший способ выполните библиотеку классов соглашение об именах, показанный `ID_FILE_OPEN`. [Стандартные команды](../mfc/standard-commands.md) описание стандартных команд, определенных в библиотеке классов.  
  
## <a name="see-also"></a>См. также  
 [Объекты пользовательского интерфейса и идентификаторы команд](../mfc/user-interface-objects-and-command-ids.md)

