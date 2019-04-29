---
title: Классы Win32 для работы в Интернете
ms.date: 09/12/2018
f1_keywords:
- vc.classes.win32
helpviewer_keywords:
- Internet classes [MFC]
- WinInet classes [MFC], classes
- Win32 [MFC], Internet classes
- Windows API [MFC], Internet classes
ms.assetid: b49601d5-3025-4068-9408-316b54ee4375
ms.openlocfilehash: c067d0c0067ee13b0e6ce6d84fd97135274c88b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326733"
---
# <a name="win32-internet-classes"></a>Классы Win32 для работы в Интернете

MFC создает оболочку для Win32 Internet (WinInet) и технология ActiveX упрощает программирование для Интернета.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

[CInternetSession](../mfc/reference/cinternetsession-class.md)<br/>
Создает и инициализирует один сеанс Интернет или несколько параллельных сеансов Интернета и, при необходимости, описывает подключение к прокси-сервер.

[CInternetConnection](../mfc/reference/cinternetconnection-class.md)<br/>
Управление подключением к интернет-серверу.

[CInternetFile](../mfc/reference/cinternetfile-class.md)<br/>
Этот класс и его производные классы обеспечивают доступ к файлам на удаленных компьютерах, использующих протоколы Интернета.

[CHttpConnection](../mfc/reference/chttpconnection-class.md)<br/>
Управление подключением к HTTP-серверу.

[CHttpFile](../mfc/reference/chttpfile-class.md)<br/>
Предоставляет возможность поиска и чтения файлов на HTTP-сервере.

[CGopherFile](../mfc/reference/cgopherfile-class.md)<br/>
Обеспечивает возможность поиска и чтения файлов на сервере gopher.

[CFtpConnection](../mfc/reference/cftpconnection-class.md)<br/>
Управление подключением к серверу FTP.

[CGopherConnection](../mfc/reference/cgopherconnection-class.md)<br/>
Управление подключением к серверу gopher.

[CFileFind](../mfc/reference/cfilefind-class.md)<br/>
Выполняет локальное и поиске файлов Интернета.

[CFtpFileFind](../mfc/reference/cftpfilefind-class.md)<br/>
Помогает в поиске файлов Интернета на FTP-серверах.

[CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)<br/>
Помогает в поиске файлов Интернета на серверах gopher.

[CGopherLocator](../mfc/reference/cgopherlocator-class.md)<br/>
Получает средство поиска gopher с сервера gopher, определяет тип средства поиска и предоставляет средство поиска `CGopherFileFind`.

[CInternetException](../mfc/reference/cinternetexception-class.md)<br/>
Представляет условие исключения, касающееся интернет-операции.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
