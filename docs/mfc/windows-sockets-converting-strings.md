---
title: Сокеты Windows. Преобразование строк
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: eaf278fc2689f0afa9ab6ff30f1294c36de5d7ac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298366"
---
# <a name="windows-sockets-converting-strings"></a>Сокеты Windows. Преобразование строк

В этой статье и в двух других статьях приведены некоторые проблемы в программировании сокетов Windows. В этой статье рассматриваются преобразования строк. Другие проблемы рассматриваются в [сокеты Windows: Блокировка](../mfc/windows-sockets-blocking.md) и [сокеты Windows: Порядок байтов](../mfc/windows-sockets-byte-ordering.md).

Если вы используете или являются производными от класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md), вам потребуется самостоятельно управлять эти проблемы. Если вы используете или являются производными от класса [CSocket](../mfc/reference/csocket-class.md), MFC автоматически управляет ими.

## <a name="converting-strings"></a>Преобразование строк

Если вы обмениваться данными между приложений, использующих строк, которые хранятся в разных форматах расширенных символов, таких как Юникода и многобайтовой кодировки (MBCS), или один из них и приложения с помощью строки символов ANSI, необходимо управлять преобразования самостоятельно под `CAsyncSocket`. `CArchive` Объект, используемый с `CSocket` управляет такое преобразование посредством возможности класса [CString](../atl-mfc-shared/reference/cstringt-class.md). Дополнительные сведения см. в спецификации Windows Sockets, расположенный в пакете Windows SDK.

Дополнительные сведения:

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)

- [Сокеты Windows. Сокеты Stream](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)
