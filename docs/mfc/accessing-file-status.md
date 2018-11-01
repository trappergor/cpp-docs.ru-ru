---
title: Доступ к состоянию файла
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: 3e16f8b11d17cd911646c3c9206d1d7deb577ef9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629792"
---
# <a name="accessing-file-status"></a>Доступ к состоянию файла

`CFile` также поддерживает получение состояния файла, включая ли файл существует, даты создания и изменения и времени, логический размер и путь.

### <a name="to-get-file-status"></a>Чтобы получить состояние файла

1. Используйте [CFile](../mfc/reference/cfile-class.md) класс для получения и задания сведений о файле. Одним из полезных приложений является использование `CFile` статическая функция-член **GetStatus** чтобы определить, существует ли файл. **GetStatus** возвращает 0, если указанный файл не существует.

Таким образом, можно использовать результат **GetStatus** для определения, следует ли использовать **CFile::modeCreate** флаг при открытии файла, как показано в следующем примере:

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

Дополнительные сведения см. в разделе [сериализации](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>См. также

[Файлы](../mfc/files-in-mfc.md)

