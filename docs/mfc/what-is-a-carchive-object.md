---
title: "Что такое объект CArchive | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb9b0c3e24094deb0d4fd4ac20d673d9ffafca6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="what-is-a-carchive-object"></a>Понятие объекта CArchive
Объект `CArchive` объект предоставляет механизм типобезопасный буферизации для записи или чтения сериализуемых объектов в `CFile` объекта. Обычно `CFile` представляет файл на диске; Однако он также может быть файл памяти (`CSharedFile` объекта), возможно, представляющий в буфер обмена.  
  
 Данный `CArchive` объекта либо хранилищ (записывает, сериализует) или загрузки данных (считывает, десериализует) данных, но не оба. Жизненного цикла `CArchive` объекта только один проход по записи объектов в файл или при чтении объектов из файла. Таким образом, два последовательно создан `CArchive` объекты необходимы для сериализации данных в файл и затем десериализовать обратно из файла.  
  
 Когда архив сохраняет объекты в файл, присоединяет архив `CRuntimeClass` имя для объектов. Затем, когда другой архив загружает объекты из файла в память, `CObject`-производных объектов воссоздаются динамически на основе `CRuntimeClass` объектов. Данный объект может ссылаться несколько раз записываются в файл путем сохранения архива. При загрузке резервной копии, однако будет восстановления объекта только один раз. Сведения о как присоединяет архив `CRuntimeClass` информацию в объекты и восстанавливает, учитывая возможные несколько ссылок, описаны в [технические Примечание 2](../mfc/tn002-persistent-object-data-format.md).  
  
 Как данные сериализуются в архив, архив накапливает данные до заполнения буфера. Затем архив записывает свой буфер в `CFile` объекта, на который указывает `CArchive` объекта. Аналогичным образом при считывании данных из архива, она считывает данные из файла в буфер, а затем из буфера Десериализованный объект. Эта буферизация уменьшает количество раз, когда жесткий диск физически считывается, тем самым повышая производительность приложения.  
  
## <a name="see-also"></a>См. также  
 [Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)

