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
ms.openlocfilehash: 52089364a6be423c69a7031cd0d99e1924de1444
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626063"
---
# <a name="clipboard-adding-other-formats"></a>Буфер обмена. Добавление других форматов

В этом разделе объясняется, как развернуть список поддерживаемых форматов, особенно для поддержки OLE. [Буфер обмена раздела. копирование и вставление данных](clipboard-copying-and-pasting-data.md) описывает минимальную реализацию, необходимую для поддержки копирования и вставления из буфера обмена. Если все это реализовано, то в буфер обмена помещаются только **CF_METAFILEPICT**, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**и, возможно, **CF_LINKSOURCE**. Большинству приложений потребуется больше форматов в буфере обмена, чем в этих трех.

## <a name="registering-custom-formats"></a><a name="_core_registering_custom_formats"></a>Регистрация пользовательских форматов

Чтобы создать собственные пользовательские форматы, выполните ту же процедуру, которая использовалась при регистрации любого пользовательского формата буфера обмена: передайте имя формата в функцию **регистерклипбоардформат** и используйте его возвращаемое значение в качестве идентификатора формата.

## <a name="placing-formats-on-the-clipboard"></a><a name="_core_placing_formats_on_the_clipboard"></a>Размещение форматов в буфере обмена

Чтобы добавить в буфер обмена дополнительные форматы, необходимо переопределить `OnGetClipboardData` функцию в классе, производном от, `COleClientItem` или `COleServerItem` (в зависимости от того, являются ли данные для копирования собственными). В этой функции следует использовать следующую процедуру.

#### <a name="to-place-formats-on-the-clipboard"></a>Размещение форматов в буфере обмена

1. Создание объекта `COleDataSource`.

1. Передайте этот источник данных в функцию, которая добавляет собственные форматы данных в список поддерживаемых форматов путем вызова метода `COleDataSource::CacheGlobalData` .

1. Добавьте стандартные форматы, вызвав `COleDataSource::CacheGlobalData` для каждого стандартного формата, который требуется поддерживать.

Этот метод используется в примере программы MFC OLE в приложении [HIERSVR](../overview/visual-cpp-samples.md) (изучите `OnGetClipboardData` функцию-член класса **ксерверитем** ). Единственное отличие в этом примере состоит в том, что третий шаг не реализован, так как HIERSVR не поддерживает другие стандартные форматы.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Объекты данных OLE и источники данных и унифицированная отправка данных](data-objects-and-data-sources-ole.md)

- [Перетаскивание OLE](drag-and-drop-ole.md)

- [OLE](ole-background.md)

## <a name="see-also"></a>См. также раздел

[Буфер обмена. Использование механизма буфера обмена OLE](clipboard-using-the-ole-clipboard-mechanism.md)
