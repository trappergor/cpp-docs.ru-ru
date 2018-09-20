---
title: 'Сокеты Windows: Преобразование строк | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b23d2149659cdad320a58bdff0f42ba113b5696
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378946"
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

