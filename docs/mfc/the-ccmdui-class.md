---
title: "Класс CCmdUI | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdUI - класс, обновление меню"
  - "панели инструментов [C++], обновление"
  - "обработчики обновлений"
  - "обновление объектов пользовательского интерфейса"
  - "объекты пользовательского интерфейса, обновление"
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CCmdUI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если он направляет команды обновления его обработчик, среда передает обработчиком указатель на объект `CCmdUI` \(или в объект `CCmdUI`\- производного класса\).  Этот объект представляет пункт меню или кнопки панели инструментов или другой объект пользовательского интерфейса, значение команды.  Вызывает обработчик обновления функции\-члены структуры `CCmdUI` посредством указателя для обновления объекта пользовательского интерфейса.  Например, ниже обработчик обновления для ясности весь пункт меню:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/CPP/the-ccmdui-class_1.cpp)]  
  
 Этот обработчик вызывает функцию\-член **Включить** объекта с доступом пункта меню.  **Включить** делает элемент доступен для использования.  
  
## См. также  
 [Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)