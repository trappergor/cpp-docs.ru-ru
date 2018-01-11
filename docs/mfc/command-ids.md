---
title: "Идентификаторы команд | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b651c734fbd7098705801aefcaa490293a4d661d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="command-ids"></a>Идентификаторы команд
Команда полностью описаны только его идентификатор команды (в кодировке **WM_COMMAND** сообщения). Этот идентификатор назначается объект пользовательского интерфейса, который формирует команды. Как правило были указаны идентификаторы функциональные возможности пользовательского интерфейса объекта, к которому они назначены.  
  
 Например, элемент "Очистить все" в меню "Правка" может быть назначен идентификатор таких как **ID_EDIT_CLEAR_ALL**. Библиотека классов есть стандартные некоторых кодов, особенно для команд, платформа обработки, такие как **ID_EDIT_CLEAR_ALL** или `ID_FILE_OPEN`. Вы создадите другие идентификаторы команд самостоятельно.  
  
 При создании собственных меню в Visual C++ редактор меню — хороший способ выполните библиотеку классов соглашение об именах, показанный `ID_FILE_OPEN`. [Стандартные команды](../mfc/standard-commands.md) описание стандартных команд, определенных в библиотеке классов.  
  
## <a name="see-also"></a>См. также  
 [Объекты пользовательского интерфейса и идентификаторы команд](../mfc/user-interface-objects-and-command-ids.md)

