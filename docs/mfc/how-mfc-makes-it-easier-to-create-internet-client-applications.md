---
title: Использование MFC для упрощения создания клиентских приложений в Интернете
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
ms.openlocfilehash: ffeed3a844fb86acf1bf8c5181c59529824c27f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405759"
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
