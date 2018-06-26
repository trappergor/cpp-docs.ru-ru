---
title: Чтение и запись файлов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e30ee5b326833b45365c422238ecfcd4f82c556d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930915"
---
# <a name="reading-and-writing-files"></a>Чтение и запись файлов
При использовании функции обработки файлов библиотеки времени выполнения C, будут отображаться знакомые MFC операций чтения и записи. В этой статье описывается непосредственно чтение и запись непосредственно в `CFile` объекта. Вы также можете буферизованный файлового ввода-вывода с [CArchive](../mfc/reference/carchive-class.md) класса.  
  
#### <a name="to-read-from-and-write-to-the-file"></a>Для чтения и записи в файл  
  
1.  Используйте `Read` и `Write` функции-члены для чтения и записи данных в файле.  
  
     - или -  
  
2.  `Seek` Функция-член также доступен для перемещения с определенным смещением в файле.  
  
 `Read` принимает указатель на буфер, и число байтов для чтения и возвращает фактическое число считанных байтов. Если требуемое количество байтов не удалось прочитать из-за конец файла (EOF) достигается, возвращается фактическое число считанных байтов. Если возникают ошибки чтения, создается исключение. `Write` Аналогично `Read`, но не возвращается число записанных байтов. Если происходит ошибка, включая все байты, указанные, но не запись, создается исключение. При наличии допустимого `CFile` объекта, можно его считывание или запись в него, как показано в следующем примере:  
  
 [!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  Обычно следует выполнять операции ввода вывода в **повторите**/**перехватывать** блок обработки исключений. Дополнительные сведения см. в разделе [обработки исключений (MFC)](../mfc/exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Файлы](../mfc/files-in-mfc.md)

