---
title: Обход механизма сериализации | Документация Майкрософт
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
ms.openlocfilehash: 25fc281e35fc07151fa609d07be540430a6a1da6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399820"
---
# <a name="bypassing-the-serialization-mechanism"></a>Обход механизма сериализации

Как вы уже видели, платформа предоставляет по умолчанию способ чтения и записи данных из файлов. Сериализация через объект архив обеспечить соответствие требованиям эффективной многих приложений. Такое приложение считывает файл целиком в память, пользователь может обновить файл и затем записывает обновленную версию на диск снова.

Тем не менее некоторые приложения работать с данными, совсем по-другому, и для этих приложений сериализации через архив не подходит. Примеры включают базы данных программы, программы, изменять только части больших файлов, программы, которые записывают текстовые файлы и программы, использующие файлы данных.

В таких случаях можно переопределить [Serialize](../mfc/reference/cobject-class.md#serialize) функция по-разному в качестве посредника действия файла через [CFile](../mfc/reference/cfile-class.md) объекта вместо [CArchive](../mfc/reference/carchive-class.md) объекта.

Можно использовать `Open`, `Read`, `Write`, `Close`, и `Seek` функции-члены класса `CFile` чтобы открыть файл, переместите указатель файла (поиск) до определенной точки в файле, считывает запись (указанное число байтов ) в таком случае пользователь сам обновить запись, а затем выполнить поиск в ту же точку и перезаписи записи в файл. Платформа будет открыт файл для вас, и можно использовать `GetFile` функция-член класса `CArchive` получить указатель на `CFile` объект. Для использования еще более сложные и гибкие, вы можете переопределить [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) и [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) функции-члены класса `CWinApp`. Дополнительные сведения см. в разделе класса [CFile](../mfc/reference/cfile-class.md) в *Справочник по библиотеке MFC*.

В этом случае ваш `Serialize` переопределение не выполняет никаких действий, например, если вы не хотите его чтение и запись в файл заголовок, чтобы сохранить ее в актуальном состоянии при закрытии документа.

## <a name="see-also"></a>См. также

[Использование документов](../mfc/using-documents.md)

