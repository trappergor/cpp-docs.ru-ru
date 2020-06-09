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
ms.openlocfilehash: 73407eba802b7640e880b821144954fa6442f177
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622160"
---
# <a name="opening-files"></a>Открытие файлов

В MFC наиболее распространенным способом открытия файла является процесс из двух этапов.

#### <a name="to-open-a-file"></a>Чтобы открыть файл

1. Создайте объект File без указания пути или флагов разрешений.

   Как правило, объект File создается путем объявления переменной [кфиле](reference/cfile-class.md) в кадре стека.

1. Вызовите функцию [Open](reference/cfile-class.md#open) Member для объекта File, указав путь и флаги разрешений.

   Возвращаемое значение для `Open` будет ненулевым, если файл был успешно открыт, или 0, если не удалось открыть указанный файл. `Open`Прототип функции-члена выглядит следующим образом:

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   Флаги открытия указывают, какие разрешения (например, только для чтения) нужно использовать для файла. Возможные значения флагов определяются в виде перечисленных констант в `CFile` классе, поэтому они уточняются на " `CFile::` ", как в `CFile::modeRead` . Используйте `CFile::modeCreate` флаг, если хотите создать файл.

В следующем примере показано, как создать новый файл с разрешением на чтение и запись (заменив любой предыдущий файл с тем же путем):

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
> В этом примере создается и открывается файл. При возникновении проблем `Open` вызов может вернуть `CFileException` объект в своем последнем параметре, как показано ниже. Макрос TRACE выводит и имя файла, и код, указывающий причину сбоя. Функцию можно вызвать, `AfxThrowFileException` Если требуются более подробные отчеты об ошибках.

## <a name="see-also"></a>См. также раздел

[Класс Кфиле](reference/cfile-class.md)<br/>
[Кфиле:: Open](reference/cfile-class.md#open)<br/>
[Файлы](files-in-mfc.md)
