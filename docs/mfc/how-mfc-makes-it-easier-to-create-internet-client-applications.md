---
title: "Использование MFC для упрощения для создания клиентских приложений в Интернете | Документы Microsoft"
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
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6270cdd3e64d24f1c2000acb9e8466f8c85edba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>Использование MFC для упрощения создания клиентских приложений в Интернете
Microsoft Foundation Classes инкапсулируют функции расширения Интернета Win32 (WinInet) таким образом, обеспечивает знакомый контекст для программистов, использующих MFC. MFC предоставляет три класса файла Интернета ([классе CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), и [CGopherFile](../mfc/reference/cgopherfile-class.md)) производными [CStdioFile](../mfc/reference/cstdiofile-class.md) класса . Не только эти классы упрощают получение и обработка данных Интернета знакомые программистам, которые использовали `CStdioFile` для локальных файлов, но эти классы можно обрабатывать локальные файлы и файлы Интернета в стабильное и прозрачным способом.  
  
 Классы MFC WinInet обеспечивают ту же функциональность, что `CStdioFile` для данных, передаваемых через Интернет. Эти классы абстрактных протоколы HTTP, FTP и gopher в приложении общий программный интерфейс, который предоставляет быстрый и простой способа создания приложений, поддерживающих Интернет. Например, для подключения к FTP-сервера по-прежнему требуется несколько шагов на низком уровне, но как разработчик MFC, необходимо только один вызов `CInternetSession::GetFTPConnection` для создания этого соединения.  
  
 Кроме того классы MFC WinInet обеспечивают следующие преимущества:  
  
-   Буфер ввода-вывода  
  
-   Обрабатывает типизированный тип данных  
  
-   Параметры по умолчанию для многих функций  
  
-   Для типичных ошибок Интернет обработки исключений  
  
-   Автоматическая очистка открытых дескрипторов и подключений  
  
## <a name="see-also"></a>См. также  
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Использование WinInet для упрощения создания клиентских приложений в Интернете](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

