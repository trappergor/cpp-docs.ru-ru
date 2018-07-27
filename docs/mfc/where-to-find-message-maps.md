---
title: Расположение схем сообщений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19dfaec7d97bed560665fce25c2ddf2cc816a483
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383397"
---
# <a name="where-to-find-message-maps"></a>Расположение схем сообщений
При создании нового каркас приложения с помощью мастера приложений приложения мастер записывает схему сообщений для каждого класса целевой объект команды, он создает для вас. Сюда входят производного приложения, документа, представления и классы окна фрейма. Эти схемы сообщений уже есть записи, предоставленные с помощью мастера приложений для определенных сообщений и встроенных команд, а некоторые — всего лишь заполнители для обработчиков, которые будут добавлены.  
  
 Схему сообщений класс находится в папке. CPP-файл для класса. Работа с картами базовое сообщение, создаваемых мастером приложений, использовании окна «Свойства» для добавления записи для сообщения и команды, которые будет обрабатывать каждый класс. Карта обычное сообщение может выглядеть следующим образом, после добавления некоторые записи:  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]  
  
 Сопоставление сообщений состоит из коллекции макросов. Два макроса [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) и [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), квадратная скобка схему сообщений. Другие макросы, такие как `ON_COMMAND`, заполните содержимое схему сообщений.  
  
> [!NOTE]
>  Макросы схемы сообщений, не следуют точка с запятой.  
  
 При использовании мастера добавления классов для создания нового класса, он содержит схему сообщений для класса. Кроме того можно создать схему сообщений вручную с помощью редактора исходного кода.  
  
## <a name="see-also"></a>См. также  
 [Выполнение платформой поиска по схемам сообщений](../mfc/how-the-framework-searches-message-maps.md)

