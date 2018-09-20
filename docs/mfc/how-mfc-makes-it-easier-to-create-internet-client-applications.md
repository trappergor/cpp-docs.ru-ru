---
title: Как MFC упрощает создание клиентских приложений в Интернете | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26380dc7e01449e4700ddf403c7395714287ed38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407170"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>Использование MFC для упрощения создания клиентских приложений в Интернете

Microsoft Foundation Classes инкапсулировать функции расширения Интернета Win32 (WinInet) способом, который предоставляет знакомые контекст для программистов, использующих MFC. MFC предоставляет три класса Интернет-файл ([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), и [CGopherFile](../mfc/reference/cgopherfile-class.md)) производным от [CStdioFile](../mfc/reference/cstdiofile-class.md) класса . Не только эти классы упрощают извлечение и обработка данных Internet знакомые программистам, которые использовали `CStdioFile` для локальных файлов, но эти классы можно обрабатывать локальные файлы и файлы Интернета согласованное и прозрачным образом.

Классы MFC WinInet обеспечивают ту же функциональность, что `CStdioFile` для данных, передаваемых через Интернет. Эти классы абстрагировать Интернет-протоколы HTTP, FTP и gopher в приложении общий интерфейс программирования, который предоставляет быстрый и простой путь для создания приложений с поддержкой Интернета. Например, подключение к FTP-сервер по-прежнему необходимо выполнить несколько действий на низком уровне, но разработчикам MFC, необходимо только один вызов `CInternetSession::GetFTPConnection` для создания этого подключения.

Кроме того классы MFC WinInet предоставляют следующие преимущества:

- Буферизации ввода-вывода

- Обрабатывает безопасных типов данных

- Параметры по умолчанию для многих функций

- Обработке исключений для распространенных ошибок Internet

- Автоматическая очистка открытых дескрипторов и подключений

## <a name="see-also"></a>См. также

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Использование WinInet для упрощения создания клиентских приложений в Интернете](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

