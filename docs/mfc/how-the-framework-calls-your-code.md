---
title: "Вызовы кода со стороны платформы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83eeb1c7fd3032ae33c213f17522b171bdb46e55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-the-framework-calls-your-code"></a>Вызовы к коду со стороны платформы
Очень важно понимать взаимосвязь между исходный код и код в платформе MFC. При запуске приложения, большая часть потока управления находится в коде платформы. Среда управляет цикл обработки сообщений, которая получает сообщения от Windows, пользователь выбирает команды и изменении данных в представлении. События, которые можно обрабатывать платформа сама по себе не следует полагаться на коде вообще. Например платформа знает, как закрыть окна и как выход из приложения в ответ на команды пользователя. Как он обрабатывает эти задачи, платформа использует дать вам возможность реагировать на эти события, а также обработчики сообщений и виртуальных функций C++. Код находится не в элемент управления, однако; Платформа —.  
  
 Платформа вызывает код для события конкретного приложения. Например, когда пользователь выбирает команду меню, платформа перенаправляет команды вдоль последовательность объектов C++: текущее окно представлений и фреймов, документ, связанный с представления, шаблон документа для документа и объект приложения. Если один из этих объектов может обработать команду, она делает это, вызов функции соответствующий обработчик сообщений. Для любой заданной команды кода, вызываемого возможно, вам или может быть framework.  
  
 Такой подход является в некоторой степени знакомые программистам, возникших с традиционного программирования для Windows или программирования на основе событий.  
  
 Щелкните ссылку считает, что платформа как она инициализирует и запускает приложение и затем производит очистку, при завершении работы приложения. Будет также понимать, где соответствует написанного кода.  
  
 Дополнительные сведения см. в разделе [класс CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md) и [шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="see-also"></a>См. также  
 [Сборка в платформе](../mfc/building-on-the-framework.md)

