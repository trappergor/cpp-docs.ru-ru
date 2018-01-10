---
title: "Поддержка OLE: Контейнеры и серверы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE full-server applications [MFC]
- server applications [MFC], communication with containers
- full-server [MFC]
- server applications [MFC], requirements
- server applications [MFC], defined
- OLE server applications [MFC], about server applications
- server applications [MFC], full-server vs. mini-server
- OLE server applications [MFC], mini-server applications
- OLE containers [MFC], container applications
- containers [MFC], OLE container applications
- server applications [MFC]
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b3c6f3c15b0ea398ec621ba5f6e34a9fb6e0aae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-containers-and-servers"></a>Поддержка OLE. Контейнеры и серверы
Приложения-контейнера — это приложение, которое может включать внедренные и связанные элементы в свои документы. Документы, управляемые приложения-контейнера должен иметь возможность хранения и отображения компонентов документов OLE, а также данные, созданные самим приложением. Приложения-контейнера необходимо также разрешить пользователям вставлять новые элементы или изменять существующие элементы, активировав серверных приложений, при необходимости. В статье перечислены требования пользовательского интерфейса из приложения контейнера [контейнеры: проблемы пользовательского интерфейса](../mfc/containers-user-interface-issues.md).  
  
 Серверное приложение или компонент приложения — это приложение, можно создавать компоненты документа OLE для использования приложением-контейнером. Серверные приложения обычно поддерживает перетаскивание или копирование свои данные в буфер обмена, чтобы приложения-контейнера можно вставлять данные в виде внедренного или связанного элемента. Приложение может быть контейнер и сервер.  
  
 Большинство серверов являются отдельными приложениями или полный серверов. они может работать как в качестве автономных приложений или могут быть запущены приложения-контейнера. Miniserver — это специальный тип серверного приложения, которые могут запускаться только в контейнере. Он не может выполняться как отдельное приложение. Примерами miniservers являются серверы Microsoft Draw и Microsoft Graph.  
  
 Контейнеры и серверы не взаимодействуют напрямую. Вместо этого они взаимодействуют через OLE системные библиотеки динамической компоновки (DLL). Эти библиотеки DLL обеспечивают функции, вызывающие контейнеры и серверы, а контейнеры и серверы также функции обратного вызова, которые вызывают библиотеки DLL.  
  
 С помощью этого средства коммуникации, контейнер не должны знать детали реализации серверного приложения. Она позволяет контейнер для принятия элементов, созданных любым сервером без определения типов серверов, с которыми можно работать. В результате пользователь приложения-контейнера можно воспользоваться преимуществами будущие версии приложений и форматов данных. Если они являются компонентами OLE, составных документов будет иметь возможность включить элементы, созданные в этих приложениях.  
  
## <a name="see-also"></a>См. также  
 [Поддержка OLE](../mfc/ole-background.md)   
 [Поддержка OLE: Реализация MFC](../mfc/ole-background-mfc-implementation.md)   
 [Контейнеры](../mfc/containers.md)   
 [Серверы](../mfc/servers.md)   
 [Контейнеры: Клиентские элементы](../mfc/containers-client-items.md)   
 [Серверы. Элементы сервера](../mfc/servers-server-items.md)

