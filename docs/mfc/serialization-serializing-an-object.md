---
title: 'Сериализация: Сериализация объекта | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e05cce1132b180ac8f1350b68d951d776a62315f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381092"
---
# <a name="serialization-serializing-an-object"></a>Сериализация. Сериализация объекта

Статья [сериализации: создание сериализуемого класса](../mfc/serialization-making-a-serializable-class.md) показано, как создать сериализуемый класс. Получив сериализуемого класса, вы можете сериализовать объекты этого класса и из файла с помощью [CArchive](../mfc/reference/carchive-class.md) объекта. В этой статье объясняется:

- [Какие объект CArchive](../mfc/what-is-a-carchive-object.md).

- [Два способа создания CArchive](../mfc/two-ways-to-create-a-carchive-object.md).

- [Как использовать CArchive <\< и >> операторы](../mfc/using-the-carchive-output-and-input-operators.md).

- [Сохранение и загрузка CObjects через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Вы можете разрешить framework создать архив сериализуемые документа или явным образом не создадите `CArchive` объекта самостоятельно. Данные можно передавать между файлом и сериализуемый объект с помощью <\< и >> операторов для `CArchive` или, в некоторых случаях, путем вызова `Serialize` функции `CObject`-производного класса.

## <a name="see-also"></a>См. также

[Сериализация](../mfc/serialization-in-mfc.md)

