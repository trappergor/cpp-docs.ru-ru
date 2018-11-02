---
title: Сокеты Windows. Преобразование строк
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: 984554c2405bf6b8ae6a522e545bcbba6ebae529
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543733"
---
# <a name="windows-sockets-converting-strings"></a>Сокеты Windows. Преобразование строк

В этой статье и в двух других статьях приведены некоторые проблемы в программировании сокетов Windows. В этой статье рассматриваются преобразования строк. Другие проблемы рассматриваются в [Windows Sockets: блокирует](../mfc/windows-sockets-blocking.md) и [Windows Sockets: порядок байтов](../mfc/windows-sockets-byte-ordering.md).

Если вы используете или являются производными от класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md), вам потребуется самостоятельно управлять эти проблемы. Если вы используете или являются производными от класса [CSocket](../mfc/reference/csocket-class.md), MFC автоматически управляет ими.

## <a name="converting-strings"></a>Преобразование строк

Если вы обмениваться данными между приложений, использующих строк, которые хранятся в разных форматах расширенных символов, таких как Юникода и многобайтовой кодировки (MBCS), или один из них и приложения с помощью строки символов ANSI, необходимо управлять преобразования самостоятельно под `CAsyncSocket`. `CArchive` Объект, используемый с `CSocket` управляет такое преобразование посредством возможности класса [CString](../atl-mfc-shared/reference/cstringt-class.md). Дополнительные сведения см. в спецификации Windows Sockets, расположенный в пакете Windows SDK.

Дополнительные сведения:

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)

- [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)

