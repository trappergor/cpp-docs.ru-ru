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
ms.openlocfilehash: f1b59516d5bba13b6f5e006f91d8ebd560543b05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372144"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Сохранение и загрузка CObjects через архив

Хранение и загрузка `CObject`с помощью архива требует дополнительного рассмотрения. В некоторых случаях следует `Serialize` вызвать функцию `CArchive` объекта, где объект `Serialize` является параметром вызова, **>>** в `CArchive`отличие от использования ** < ** или оператора . Важным фактом является то, `CArchive` **>>** что оператор `CObject` строит память `CRuntimeClass` на основе информации, ранее записанной в файл архивом хранения.

`CArchive` ** < ** Поэтому, используете ли **>>** вы и `Serialize`операторы, по сравнению с вызовом, зависит от `CRuntimeClass` того, *нужен* ли вам архив загрузки для динамической реконструкции объекта на основе ранее хранимой информации. Используйте `Serialize` функцию в следующих случаях:

- При десериализации объекта вы заранее знаете точный класс объекта.

- При десериализации объекта для него уже выделена память.

> [!CAUTION]
> Если вы загружаете объект с помощью `Serialize` `Serialize` функции, необходимо также хранить объект с помощью функции. Не храните с `CArchive` **<<** помощью оператора, `Serialize` а затем загрузить `Serialize` с помощью `CArchive >>` функции, или хранить с помощью функции, а затем загрузить с помощью оператора.

Следующий пример иллюстрирует случаи:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Таким образом, если ваш серийный класс `CObject` определяет встроенный элемент, `CArchive` ** < ** вы **>>** *не* должны использовать и `Serialize` операторов для этого объекта, а следует вызвать функцию вместо этого. Кроме того, если ваш серийный класс определяет `CObject` указатель на (или объект, полученный от) `CObject`в качестве члена, но строит `Serialize`этот другой объект в своем собственном конструкторе, вы также должны вызвать .

## <a name="see-also"></a>См. также раздел

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)
