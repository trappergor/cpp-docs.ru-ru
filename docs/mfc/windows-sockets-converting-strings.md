---
title: 'Сокеты Windows: Преобразование строки | Документы Microsoft'
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
ms.openlocfilehash: bad57be68ce716cddf2ce44f12e94c545a7bbfd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-converting-strings"></a>Сокеты Windows. Преобразование строк
В этой статье и в двух статей дополнительное приведены некоторые проблемы в программировании Windows Sockets. В этой статье рассматриваются преобразования строк. Другие проблемы рассматриваются в [Windows Sockets: блокирование](../mfc/windows-sockets-blocking.md) и [Windows Sockets: порядок байтов](../mfc/windows-sockets-byte-ordering.md).  
  
 Если вы используете или являются производными от класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md), потребуется самостоятельно управлять эти проблемы. Если вы используете или являются производными от класса [CSocket](../mfc/reference/csocket-class.md), MFC автоматически управляет ими.  
  
## <a name="converting-strings"></a>Преобразование строк  
 При обмене данными между приложениями, использующими строк, которые хранятся в различных форматах расширенных символов, таких как Юникода и многобайтовой кодировки (MBCS) или от одного из этих и приложения с помощью строки символов ANSI, необходимо управлять преобразования самостоятельно под `CAsyncSocket`. `CArchive` Объект, используемый с `CSocket` управляет такое преобразование через возможности класса [CString](../atl-mfc-shared/reference/cstringt-class.md). Дополнительные сведения см. в спецификации Windows Sockets, расположенный в Windows SDK.  
  
 Дополнительные сведения:  
  
-   [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)  
  
-   [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)

