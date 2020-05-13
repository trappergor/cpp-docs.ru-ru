---
title: Два способа создать объект CArchive
ms.date: 11/04/2016
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
ms.openlocfilehash: 71592584d4ecdd3169ad894861a97fa668c04ee8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370948"
---
# <a name="two-ways-to-create-a-carchive-object"></a>Два способа создать объект CArchive

Существует два способа создания `CArchive` объекта:

- [Неявное создание объекта CArchive через рамки](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [Явное создание объекта CArchive](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>Неявное создание объекта CArchive через рамки

Самый распространенный и простой способ — `CArchive` позволить инфраструктуре создать объект для документа от имени команд «Сохранить», сохранить as и открыть в меню файлов.

Вот что делает фреймворк, когда пользователь приложения выдает команду «Сохранить как» из меню «Файл»:

1. Представляет поле для диалога **Save As** и получает имя файла от пользователя.

1. Открывает файл, названный пользователем в `CFile` качестве объекта.

1. Создает `CArchive` объект, упомянение на этот `CFile` объект. При создании `CArchive` объекта фреймворк устанавливает режим "хранить" (написать, сериализовать), в отличие от "нагрузки" (читай, десериализировать).

1. Вызывает `Serialize` функцию, `CDocument`определяемую в вашем классе, передавая ее ссылкой на `CArchive` объект.

`Serialize` Функция документа затем записывает данные на объект, как это объясняется в ближайшее `CArchive` время. По возвращении `Serialize` из функции, `CArchive` фреймворк уничтожает объект, а затем `CFile` объект.

Таким образом, если вы `CArchive` позволите инфраструктуре создать объект для вашего документа, все, что вам нужно сделать, это реализовать `Serialize` функцию документа, которая записывает и читает в архив и из него. Вы также должны `Serialize` реализовать `CObject`для любых полученных объектов, которые `Serialize` функция документа, в свою очередь, сериализирует прямо или косвенно.

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a>Явное создание объекта CArchive

Помимо сериализации документа через платформу, есть и `CArchive` другие случаи, когда вам может понадобиться объект. Например, можно выставить данные в и из Clipboard, `CSharedFile` представленные объектом. Или вы можете использовать пользовательский интерфейс для сохранения файла, который отличается от файла, предложенного инфраструктурой. В этом случае можно явно `CArchive` создать объект. Вы делаете это так же, как и фреймворк, используя следующую процедуру.

#### <a name="to-explicitly-create-a-carchive-object"></a>Явно создать объект CArchive

1. Построить `CFile` объект или объект, `CFile`полученный из .

1. Передайте `CFile` объект конструктору `CArchive`для, как показано в следующем примере:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   Вторым аргументом `CArchive` для конструктора является перечисленное значение, которое определяет, будет ли архив использоваться для хранения или загрузки данных в файл или из нее. Функция `Serialize` объекта проверяет это состояние, `IsStoring` вызывая функцию для объекта архива.

Когда вы закончите хранить или загружать `CArchive` данные на объект или из него, закройте их. Хотя `CArchive` (и) `CFile`объекты будут автоматически закрывать архив (и файл), это хорошая практика, чтобы явно сделать это, поскольку он делает восстановление от ошибок легче. Для получения дополнительной информации об [Exceptions: Catching and Deleting Exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md)обработке ошибок см.

#### <a name="to-close-the-carchive-object"></a>Закрытие объекта CArchive

1. Следующий пример иллюстрирует, как `CArchive` закрыть объект:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)
