---
title: Сохранение и загрузка CObjects через архив
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: 368421a86d6ff6fc70455edd0ea9a32e05645007
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446360"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Сохранение и загрузка CObjects через архив

Хранение и загрузка `CObject`с помощью архива требует дополнительного рассмотрения. В некоторых случаях следует вызывать функцию `Serialize` объекта, где объект `CArchive` является параметром вызова `Serialize`, в отличие от оператора **<\<** или **>>** `CArchive`. Важно помнить, что оператор `CArchive` **>>** конструирует `CObject` в памяти на основе `CRuntimeClass` сведений, ранее записанных в файл в архиве хранения.

Таким образом, если вы используете операторы `CArchive` **<\<** и **>>** , а также вызываете `Serialize`, зависит от того, *нужен* ли Архив загрузки для динамического восстановления объекта на основе ранее сохраненной информации `CRuntimeClass`. Используйте функцию `Serialize` в следующих случаях:

- При десериализации объекта необходимо заранее понять точный класс объекта.

- При десериализации объекта для него уже выделяется память.

> [!CAUTION]
>  При загрузке объекта с помощью функции `Serialize` необходимо также сохранить объект с помощью функции `Serialize`. Не сохраняйте с помощью оператора `CArchive` **<<** , затем загрузите с помощью функции `Serialize` или сохраните с помощью функции `Serialize`, а затем загрузите с помощью оператора `CArchive >>`.

В следующем примере показаны варианты:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

В целом, если сериализуемый класс определяет внедренный `CObject` как член, *не* следует использовать операторы `CArchive` **<\<** и **>>** для этого объекта, но вместо этого следует вызывать функцию `Serialize`. Кроме того, если сериализуемый класс определяет указатель на `CObject` (или объект, производный от `CObject`) в качестве члена, но конструирует этот другой объект в собственном конструкторе, необходимо также вызвать метод `Serialize`.

## <a name="see-also"></a>См. также раздел

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)
