---
title: "Сообщения | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сообщения"
  - "сообщения, MFC - библиотека"
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Сообщения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Цикл обработки сообщений в функцию\-член **Запуск** класса `CWinApp` извлекает очереди сообщений, созданные разными событиями.  Например, если пользователь щелкает мышью, Windows отправляет несколько мышь\- связанных сообщений, например, `WM_LBUTTONDOWN`, если была нажата левая кнопка мыши и `WM_LBUTTONUP` при нажатой сигнал.  Реализация платформы цикла обработки сообщений приложения отправляет сообщение с соответствующим окно.  
  
 Важные категории сообщений описаны в разделе [Категории сообщения](../mfc/message-categories.md).  
  
## См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)