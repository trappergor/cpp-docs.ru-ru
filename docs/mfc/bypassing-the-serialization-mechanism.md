---
title: Обход механизма сериализации | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9252e08fe672f111dcf2b289b1b12891022a318d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931092"
---
# <a name="bypassing-the-serialization-mechanism"></a>Обход механизма сериализации
Как видно, платформа предоставляет по умолчанию способ чтения и записи данных из файлов. Сериализация через объект архив потребностям эффективной многих приложений. Такое приложение считывает файл целиком в память, пользователь может обновить файл и затем записывает обновленную версию на диск, еще раз.  
  
 Тем не менее некоторые приложения работать с данными очень по-разному, и для этих приложений сериализации через архив не подходит. Например, база данных программы, программы, изменять части больших файлов, программы, которые записывают текстовые файлы и программы, которые совместно использовать файлы данных.  
  
 В этих случаях можно переопределить [сериализации](../mfc/reference/cobject-class.md#serialize) функции по-разному для посредничества действия файл через [CFile](../mfc/reference/cfile-class.md) объекта, а не [CArchive](../mfc/reference/carchive-class.md) объекта.  
  
 Можно использовать `Open`, `Read`, `Write`, `Close`, и `Seek` функции-члены класса `CFile` открыть файл, переместить указатель на файл (поиск), на определенный момент в файл, считывает запись (с указанным числом байтов ) на этом этапе позволяют обновить запись, затем снова выполнить поиск по той же точке и записать обратно в файл. Платформа будет открыт файл автоматически, и можно использовать `GetFile` функции-члена класса `CArchive` для получения указателя на `CFile` объекта. Для использования даже более сложные и гибким, можно переопределить [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) и [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) функции-члены класса `CWinApp`. Дополнительные сведения см. в разделе класса [CFile](../mfc/reference/cfile-class.md) в *Справочник по библиотеке MFC*.  
  
 В этом сценарии ваш `Serialize` переопределение не выполняет никаких действий, если, например, вам не нужно для его чтения и записи заголовок файла, чтобы он был в актуальном состоянии при закрытии документа.  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

