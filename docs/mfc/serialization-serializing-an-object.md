---
title: Сериализация. Сериализация объекта
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: 5c1106f180c587894283575a82a88e9e18b5c01a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290499"
---
# <a name="serialization-serializing-an-object"></a>Сериализация. Сериализация объекта

Статья [сериализации: Создание сериализуемого класса](../mfc/serialization-making-a-serializable-class.md) показано, как создать сериализуемый класс. Получив сериализуемого класса, вы можете сериализовать объекты этого класса и из файла с помощью [CArchive](../mfc/reference/carchive-class.md) объекта. В этой статье объясняется:

- [Какие объект CArchive](../mfc/what-is-a-carchive-object.md).

- [Два способа создания CArchive](../mfc/two-ways-to-create-a-carchive-object.md).

- [Как использовать CArchive <\< и >> операторы](../mfc/using-the-carchive-output-and-input-operators.md).

- [Сохранение и загрузка CObjects через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Вы можете разрешить framework создать архив сериализуемые документа или явным образом не создадите `CArchive` объекта самостоятельно. Данные можно передавать между файлом и сериализуемый объект с помощью <\< и >> операторов для `CArchive` или, в некоторых случаях, путем вызова `Serialize` функции `CObject`-производного класса.

## <a name="see-also"></a>См. также

[Сериализация](../mfc/serialization-in-mfc.md)
