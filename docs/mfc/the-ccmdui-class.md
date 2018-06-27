---
title: Класс CCmdUI | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a857d1cddcc78c7cfff4243b9c99194986af3d9b
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956490"
---
# <a name="the-ccmdui-class"></a>Класс CCmdUI
Когда он направляет его обработчик команды update, платформа передает обработчик указатель `CCmdUI` объекта (или в объект `CCmdUI`-производного класса). Этот объект представляет элемент меню или панели инструментов кнопку или другой объект пользовательского интерфейса, вызвавшего команду. Обработчик обновлений вызывает член функции `CCmdUI` структуры через указатель для обновления объекта пользовательского интерфейса. Например вот обработчика обновлений, очистить все пункта меню.  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 Этот обработчик вызывает `Enable` функции-члена объекта с доступом к пункту меню. `Enable` Создает элемент, доступный для использования.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)

