---
title: Открытие файлов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 379449469d37f01c7c0fd225688a019eaec9e977
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352767"
---
# <a name="opening-files"></a>Открытие файлов
В MFC наиболее распространенный способ открытия файла является двухэтапный процесс.  
  
#### <a name="to-open-a-file"></a>Для открытия файла  
  
1.  Создайте объект файла без указания пути, или разрешение флаги.  
  
     Обычно создается путем объявления объекта файла [CFile](../mfc/reference/cfile-class.md) переменной в кадре стека.  
  
2.  Вызовите [откройте](../mfc/reference/cfile-class.md#open) функции-члена для объекта файла, указав путь и разрешение флаги.  
  
     Возвращаемое значение для `Open` будет ненулевое значение, если файл был успешно открыт, или 0, если не удалось открыть указанный файл. `Open` Функция-член является прототипом следующим образом:  
  
     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`  
  
     Флаги open например указать, какие разрешения только для чтения, необходимые для файла. Флаг возможные значения определяются как перечислимых констант в `CFile` класса так, чтобы они указывать «`CFile::`» в качестве `CFile::modeRead`. Используйте `CFile::modeCreate` флаг, чтобы создать файл.  
  
 В следующем примере показано, как создать новый файл с разрешениями чтения и записи (заменив любой предыдущий файл с тем же путем):  
  
 [!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]  
  
> [!NOTE]
>  Этот пример создает и открывает файл. При наличии проблем, `Open` вызов может быть возвращен `CFileException` объекта в его последнего параметра, как показано ниже. `TRACE` Макрос выводит имя файла и код, указывающий причину сбоя. Можно вызвать `AfxThrowFileException` функционировать, если требуются более подробные сообщения об ошибках.  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../mfc/reference/cfile-class.md)   
 [CFile::Open](../mfc/reference/cfile-class.md#open)   
 [Файлы](../mfc/files-in-mfc.md)

