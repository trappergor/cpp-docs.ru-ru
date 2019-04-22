---
title: Буфер обмена. Добавление других форматов
ms.date: 11/04/2016
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
ms.openlocfilehash: 182abe71ccc9552c113ebb114b4351178e48b096
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766851"
---
# <a name="clipboard-adding-other-formats"></a>Буфер обмена. Добавление других форматов

В этом разделе объясняется, как расширить список поддерживаемых форматов, особенно для поддержки OLE. Раздел [буфер обмена: Копирование и вставка данных](../mfc/clipboard-copying-and-pasting-data.md) описывается минимальная реализация необходимость поддержки копирования и вставки из буфера обмена. Если все реализации, являются единственными форматами, буфер обмена **CF_METAFILEPICT**, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**и, возможно, **CF_LINKSOURCE**. В большинстве приложений потребуется другие форматы, в буфер обмена, чем эти три.

##  <a name="_core_registering_custom_formats"></a> Регистрация пользовательских форматов

Чтобы создать собственный пользовательский формат, выполните ту же процедуру, можно использовать при регистрации любого пользовательского формата буфера обмена: передайте имя формата **RegisterClipboardFormat** функции и использовать ее возвращаемое значение как идентификатор формата.

##  <a name="_core_placing_formats_on_the_clipboard"></a> Размещение форматов в буфере обмена

Чтобы добавить дополнительные форматы которые помещены в буфер обмена, необходимо переопределить `OnGetClipboardData` функцию в классе, произведенный от любого `COleClientItem` или `COleServerItem` (в зависимости от данных для копирования native). В этой функции следует использовать следующую процедуру.

#### <a name="to-place-formats-on-the-clipboard"></a>Чтобы поместить форматов в буфер обмена

1. Создание объекта `COleDataSource`.

1. Передайте этот источник данных на функцию, которая добавляет ваши собственные форматы данных в список поддерживаемых форматов путем вызова `COleDataSource::CacheGlobalData`.

1. Добавлять стандартные форматы с помощью вызова `COleDataSource::CacheGlobalData` для каждого стандартного формата, которую требуется поддерживать.

Этот метод используется в программе MFC OLE образец [HIERSVR](../overview/visual-cpp-samples.md) (проверьте `OnGetClipboardData` функцию-член **CServerItem** класса). В этом образце отличается только этот шаг еще три не реализован, поскольку HIERSVR поддерживает другие стандартные форматы.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Объекты и данные источников данных OLE и универсальный код передачи данных](../mfc/data-objects-and-data-sources-ole.md)

- [Перетаскивание OLE](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>См. также

[Буфер обмена. Использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
