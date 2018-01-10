---
title: "Класс CCmdUI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CCmdUI
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efb87fc04ee9ee55806ec4fc1103ded42231b433
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="the-ccmdui-class"></a>Класс CCmdUI
Когда он направляет его обработчик команды update, платформа передает обработчик указатель `CCmdUI` объекта (или в объект `CCmdUI`-производного класса). Этот объект представляет элемент меню или панели инструментов кнопку или другой объект пользовательского интерфейса, вызвавшего команду. Обработчик обновлений вызывает член функции `CCmdUI` структуры через указатель для обновления объекта пользовательского интерфейса. Например вот обработчика обновлений, очистить все пункта меню.  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 Этот обработчик вызывает **включить** функции-члена объекта с доступом к пункту меню. **Включить** делает элемент доступным для использования.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)

