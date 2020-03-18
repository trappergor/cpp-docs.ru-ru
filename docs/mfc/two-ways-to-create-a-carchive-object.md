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
ms.openlocfilehash: 38642906b0973730149ed0de5381519f06d69fe5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442039"
---
# <a name="two-ways-to-create-a-carchive-object"></a>Два способа создать объект CArchive

Существует два способа создания объекта `CArchive`.

- [Неявное создание объекта CArchive через платформу](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [Явное создание объекта CArchive](#_core_explicit_creation_of_a_carchive_object)

##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>Неявное создание объекта CArchive через платформу

Самый распространенный и простой способ — позволить платформе создать объект `CArchive` для документа от имени команд Сохранить, сохранить как и открыть в меню файл.

Ниже показано, что делает платформа, когда пользователь приложения выдает команду "Сохранить как" из меню "файл":

1. Представляет диалоговое окно **Сохранить как** и получает имя файла от пользователя.

1. Открывает файл с именем пользователя в качестве объекта `CFile`.

1. Создает объект `CArchive`, указывающий на этот `CFile` объект. При создании объекта `CArchive` платформа устанавливает для режима значение "Store" (запись, сериализация), а не "Load" (чтение, десериализация).

1. Вызывает функцию `Serialize`, определенную в классе, производном от `CDocument`, передавая ему ссылку на объект `CArchive`.

Затем функция `Serialize` документа записывает данные в объект `CArchive`, как описано ниже. После возврата из функции `Serialize` Framework уничтожает объект `CArchive`, а затем объект `CFile`.

Таким же, если вы разрешите платформе создать объект `CArchive` для документа, все, что нужно сделать, — это реализовать функцию `Serialize` документа, которая записывает и считывает Архив. Также необходимо реализовать `Serialize` для любых объектов, производных от `CObject`, которые функция `Serialize` документа, в свою очередь, напрямую или косвенно сериализует.

##  <a name="_core_explicit_creation_of_a_carchive_object"></a>Явное создание объекта CArchive

Помимо сериализации документа с помощью платформы существуют и другие случаи, когда может потребоваться объект `CArchive`. Например, может потребоваться сериализовать данные в буфер обмена и из него, представленные объектом `CSharedFile`. Или же можно использовать пользовательский интерфейс для сохранения файла, отличающегося от платформы, предлагаемой платформой. В этом случае можно явно создать объект `CArchive`. Это выполняется так же, как платформа, с помощью следующей процедуры.

#### <a name="to-explicitly-create-a-carchive-object"></a>Явное создание объекта CArchive

1. Создайте объект `CFile` или объект, производный от `CFile`.

1. Передайте объект `CFile` в конструктор для `CArchive`, как показано в следующем примере:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   Вторым аргументом конструктора `CArchive` является перечислимое значение, которое указывает, будет ли Архив использоваться для хранения или загрузки данных в файл или из него. Функция `Serialize` объекта проверяет это состояние, вызывая функцию `IsStoring` для объекта архива.

Завершив сохранение или загрузку данных в объект `CArchive`, закройте его. Несмотря на то, что объекты `CArchive` (и `CFile`) автоматически закрывают Архив (и файл), рекомендуется явно сделать это, так как он упрощает восстановление из-за ошибок. Дополнительные сведения об обработке ошибок см. в статье [исключения: перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md).

#### <a name="to-close-the-carchive-object"></a>Закрытие объекта CArchive

1. В следующем примере показано, как закрыть объект `CArchive`.

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)
