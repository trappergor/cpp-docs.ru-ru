---
title: Открытие файлов
ms.date: 11/04/2016
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
ms.openlocfilehash: 6119bf922b05c30a14d8421800e3931c4a038779
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375962"
---
# <a name="opening-files"></a>Открытие файлов

В MFC наиболее распространенным способом открытия файла является двухэтапный процесс.

#### <a name="to-open-a-file"></a>Чтобы открыть файл

1. Создайте объект файла без указания флагов пути или разрешения.

   Обычно вы создаете объект файла, объявляя переменную [CFile](../mfc/reference/cfile-class.md) на кадре стека.

1. Вызов функции [«Открытый](../mfc/reference/cfile-class.md#open) член» для объекта файла, поставляя флаги пути и разрешения.

   Значение возврата `Open` будет незерновым, если файл был открыт успешно или 0, если указанный файл не может быть открыт. Функция `Open` участника является прототипом:

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   Открытые флаги указывают, какие разрешения, такие как только для чтения, нужны для файла. Возможные значения флага определяются как перечисленные `CFile` константы в классе, поэтому они квалифицированы с «как`CFile::`в `CFile::modeRead`. Используйте `CFile::modeCreate` флаг, если вы хотите создать файл.

В следующем примере показано, как создать новый файл с разрешением на чтение/запись (заменяя любой предыдущий файл тем же способом):

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
> Этот пример создает и открывает файл. При наличии проблем `Open` вызов может `CFileException` вернуть объект в его последнем параметре, как показано здесь. Макрос TRACE печатает как имя файла, так и код, указывающий причину сбоя. Вы можете `AfxThrowFileException` вызвать функцию, если требуется более подробная отчетность об ошибках.

## <a name="see-also"></a>См. также раздел

[Класс CFile](../mfc/reference/cfile-class.md)<br/>
[CFile::Открыто](../mfc/reference/cfile-class.md#open)<br/>
[Файлы](../mfc/files-in-mfc.md)
