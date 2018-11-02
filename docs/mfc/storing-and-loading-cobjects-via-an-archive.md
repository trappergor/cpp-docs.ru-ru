---
title: Сохранение и загрузка CObjects через архив
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: 370e8202d1bd1cda04edbdbd12bd936bdf5ef7b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493695"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Сохранение и загрузка CObjects через архив

Сохранение и загрузка `CObject`s через архив требует дополнительных соображений. В некоторых случаях следует вызывать `Serialize` функции объекта, где `CArchive` объект является параметром `Serialize` вызова, а не с помощью **< \<** или **>>** оператор `CArchive`. Важные факты следует учитывать является то, что `CArchive` **>>** конструкции оператор `CObject` в памяти, на основе `CRuntimeClass` сведения, ранее записанным в файл хранения архива.

Таким образом, использование `CArchive` **< \<** и **>>** операторы, и вызов `Serialize`, зависит от того вы *требуется* загрузки архива для динамически воссоздания объекта на основе ранее сохраненные `CRuntimeClass` сведения. Используйте `Serialize` функции в следующих случаях:

- При десериализации объекта, вы знаете точный класс объекта, заранее.

- При десериализации объекта, уже есть память, выделенную для него.

> [!CAUTION]
>  Если загрузить объект с помощью `Serialize` функцию, необходимо также сохранить объект с помощью `Serialize` функции. Не храните с помощью `CArchive` **<<** оператор и затем нагрузки с помощью `Serialize` функцию, или сохранить с помощью `Serialize` функции, а затем загрузить с помощью `CArchive >>` оператор.

В следующем примере показано вариантов:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Таким образом, если сериализуемый класс определяет встроенный `CObject` как член, вы должны *не* использовать `CArchive` **< \<** и **>>** операторы для этого объекта, но должны вызывать `Serialize` вместо этого функцию. Кроме того Если сериализуемый класс определяет указатель на `CObject` (или объекта, производного от `CObject`) как член, но конструкции этот объект в собственный конструктор, вам также следует вызвать `Serialize`.

## <a name="see-also"></a>См. также

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)

