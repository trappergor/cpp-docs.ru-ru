---
title: Использование MFC для упрощения создания клиентских приложений в Интернете
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
ms.openlocfilehash: 71b72a3079cd0d0c87289c1813c09a24d9f75c89
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618560"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>Использование MFC для упрощения создания клиентских приложений в Интернете

Microsoft Foundation Classes инкапсулировать функции расширения Интернета (WinInet) Win32 способом, который предоставляет привычный контекст для программистов MFC. MFC предоставляет три класса файлов Интернета ([Цинтернетфиле](reference/cinternetfile-class.md), [чттпфиле](reference/chttpfile-class.md)и [CGopherFile](reference/cgopherfile-class.md)), производных от класса [кстдиофиле](reference/cstdiofile-class.md) . Эти классы не только позволяют извлекать и манипулировать данными в Интернете, знакомыми программистам, которые использовались `CStdioFile` для локальных файлов, но с этими классами можно единообразно и прозрачно управлять локальными файлами и файлами Интернета.

Классы MFC WinInet предоставляют те же функциональные возможности, что и `CStdioFile` для данных, передаваемых через Интернет. Эти классы являются абстрактными протоколами Интернета для HTTP, FTP и Gopher в интерфейс программирования приложений высокого уровня, что обеспечивает быстрый и простой путь к приложениям, поддерживающим Интернет. Например, для подключения к FTP-серверу по-прежнему требуется несколько шагов на низком уровне, но в качестве разработчика MFC необходимо только один вызов для `CInternetSession::GetFTPConnection` создания этого подключения.

Кроме того, классы MFC WinInet предоставляют следующие преимущества:

- Буферизованный ввод-вывод

- Строго типизированные дескрипторы для ваших данных

- Параметры по умолчанию для многих функций

- Обработка исключений для распространенных ошибок Интернета

- Автоматическая очистка открытых дескрипторов и соединений

## <a name="see-also"></a>См. также раздел

[Расширения Интернета Win32 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[Использование WinInet для упрощения создания клиентских приложений в Интернете](how-wininet-makes-it-easier-to-create-internet-client-applications.md)
