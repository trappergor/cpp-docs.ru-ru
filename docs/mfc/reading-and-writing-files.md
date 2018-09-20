---
title: Чтение и запись файлов | Документация Майкрософт
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
ms.openlocfilehash: d0fd41c085b9498d3f1ebb76378a83cce464142a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404076"
---
# <a name="reading-and-writing-files"></a>Чтение и запись файлов

Если вы использовали функции обработки файлов библиотеки времени выполнения C, MFC, операций чтения и записи будут отображаться знакомы. В этой статье описывается непосредственно чтение и запись непосредственно на `CFile` объекта. Вы можете также в буфер файлового ввода-вывода с [CArchive](../mfc/reference/carchive-class.md) класса.

#### <a name="to-read-from-and-write-to-the-file"></a>Для чтения и записи в файл

1. Используйте `Read` и `Write` функции-члены для чтения и записи данных в файле.

     - или -

1. `Seek` Функция-член также доступна для перемещения к определенным смещением в файле.

`Read` принимает указатель на буфер и число байтов для чтения и возвращает фактическое число считанных байтов. Если необходимое количество байт не удалось прочитать из-за конец файла (EOF) будет достигнут, возвращается фактическое число считанных байтов. Если возникают ошибки чтения, создается исключение. `Write` аналогичен `Read`, но не возвращается число записанных байтов. Если происходит ошибка, включая не записывает все байты, указанные, создается исключение. Если у вас есть допустимый `CFile` объекта, можно его считывание или запись в него, как показано в следующем примере:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
>  Обычно должно предварительно выполнить все операции ввода вывода в **попробуйте**/**catch** блоке обработки исключений. Дополнительные сведения см. в разделе [обработка исключений (MFC)](../mfc/exception-handling-in-mfc.md).

## <a name="see-also"></a>См. также

[Файлы](../mfc/files-in-mfc.md)

