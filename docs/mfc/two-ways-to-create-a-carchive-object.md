---
title: Два способа создать объект CArchive | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 630cdd1614aa19ec3a5a654d7dc4bfe7336ce027
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080589"
---
# <a name="two-ways-to-create-a-carchive-object"></a>Два способа создать объект CArchive

Существует два способа создания `CArchive` объекта:

- [Неявное создание объекта CArchive с помощью платформы](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [Явное создание объекта CArchive](#_core_explicit_creation_of_a_carchive_object)

##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> Неявное создание объекта CArchive с помощью платформы

Наиболее распространенный и простой, рекомендуется создать платформа `CArchive` объект документа от имени сохранение, сохранение и открыть команды в меню "файл".

Вот, что платформа делает когда пользователь дает команду Сохранить как, из меню "файл":

1. Представляет **Сохранить как** диалоговое окно и получает имя файла от пользователя.

1. Открывает файл с именем пользователем как `CFile` объекта.

1. Создает `CArchive` объект, указывающий на это `CFile` объекта. При создании `CArchive` объекта, платформа задает режим для «хранения» (записи, сериализации), в отличие от «загрузка» (чтение, десериализации).

1. Вызовы `Serialize` функции, определенной в вашей `CDocument`-производного класса, передавая ему ссылку на `CArchive` объекта.

В документе `Serialize` функция затем записывает данные в `CArchive` объекта, как описано в ближайшее время. После возврата из вашей `Serialize` функции платформы уничтожает `CArchive` объекта и затем `CFile` объекта.

Таким образом Если платформа создания `CArchive` объект документа, что необходимо сделать реализуют документа `Serialize` функцию, которая записывает и читает и из архива. Необходимо также реализовать `Serialize` для любого `CObject`-объекты, производные от, документа `Serialize` функция в свою очередь выполняет сериализацию прямо или косвенно.

##  <a name="_core_explicit_creation_of_a_carchive_object"></a> Явное создание объекта CArchive

Помимо сериализации документа с помощью платформы, существуют другие случаи, когда может потребоваться `CArchive` объекта. Например, может потребоваться сериализации данных в и из буфера обмена, представленный `CSharedFile` объекта. Или, возможно, вы хотите использовать пользовательский интерфейс для сохранения файла, который отличается от того, предоставляемых средой. В этом случае можно явно создать `CArchive` объекта. Это делается так же, что платформа делает, выполнив указанные ниже действия.

#### <a name="to-explicitly-create-a-carchive-object"></a>Чтобы явно создать объект CArchive

1. Создать `CFile` объект или объект, производный от `CFile`.

1. Передайте `CFile` конструктору для `CArchive`, как показано в следующем примере:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   Второй аргумент `CArchive` конструктор является значение перечисления, которое указывает, используется ли для сохранения или загрузки данных в или из файла архива. `Serialize` Функция объекта проверяет это состояние, вызвав `IsStoring` функцией для объекта архива.

Когда вы закончите, сохранения или загрузки данных из `CArchive` объекта, закройте его. Несмотря на то что `CArchive` (и `CFile`) объекты автоматически закроется архива (и файл), рекомендуется явно сделать это, так как это упрощает восстановление после ошибки. Дополнительные сведения об обработке ошибок см. в статье [исключений: исключения для перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).

#### <a name="to-close-the-carchive-object"></a>Чтобы закрыть объект CArchive

1. В следующем примере показано, как закрыть `CArchive` объекта:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>См. также

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)

