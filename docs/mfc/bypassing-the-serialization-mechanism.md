---
title: "Обход механизма сериализации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 510e6ed244fb8920c55c4b3ffedcbd0801c3e202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bypassing-the-serialization-mechanism"></a>Обход механизма сериализации
Как видно, платформа предоставляет по умолчанию способ чтения и записи данных из файлов. Сериализация через объект архив потребностям эффективной многих приложений. Такое приложение считывает файл целиком в память, пользователь может обновить файл и затем записывает обновленную версию на диск, еще раз.  
  
 Тем не менее некоторые приложения работать с данными очень по-разному, и для этих приложений сериализации через архив не подходит. Например, база данных программы, программы, изменять части больших файлов, программы, которые записывают текстовые файлы и программы, которые совместно использовать файлы данных.  
  
 В этих случаях можно переопределить [сериализации](../mfc/reference/cobject-class.md#serialize) функции по-разному для посредничества действия файл через [CFile](../mfc/reference/cfile-class.md) объекта, а не [CArchive](../mfc/reference/carchive-class.md) объекта.  
  
 Можно использовать **откройте**, **чтения**, **записи**, **закрыть**, и `Seek` функции-члены класса `CFile` для открытия файла , переместить указатель на файл (поиск), на определенный момент в файле, в этот момент чтение записи (указанное число байтов), позволяют обновление пользователя записи, затем поиск еще раз в одной точке и записи, запись обратно в файл. Платформа будет открыт файл автоматически, и можно использовать `GetFile` функции-члена класса `CArchive` для получения указателя на `CFile` объекта. Для использования даже более сложные и гибким, можно переопределить [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) и [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) функции-члены класса `CWinApp`. Дополнительные сведения см. в разделе класса [CFile](../mfc/reference/cfile-class.md) в *Справочник по библиотеке MFC*.  
  
 В этом сценарии ваш `Serialize` переопределение не выполняет никаких действий, если, например, вам не нужно для его чтения и записи заголовок файла, чтобы он был в актуальном состоянии при закрытии документа.  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

