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
ms.openlocfilehash: 23c626940e700d3e9827ef6a7cf849d970e40d5d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619779"
---
# <a name="accessing-file-status"></a>Доступ к состоянию файла

`CFile`также поддерживает получение сведений о состоянии файла, включая наличие файла, дату и время создания и изменения, логический размер и путь.

### <a name="to-get-file-status"></a>Получение состояния файла

1. Используйте класс [кфиле](reference/cfile-class.md) для получения и задания сведений о файле. Одним из полезных приложений является использование `CFile` статической функции-члена с **состоянием** "очень", чтобы определить, существует ли файл. Функция **OnStatus** возвращает 0, если указанный файл не существует.

Таким образом, можно использовать результат с параметром- **Status** , чтобы определить, следует ли использовать флаг **Кфиле:: модекреате** при открытии файла, как показано в следующем примере:

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

Связанные сведения см. в разделе [сериализация](serialization-in-mfc.md).

## <a name="see-also"></a>См. также раздел

[Файлы](files-in-mfc.md)
