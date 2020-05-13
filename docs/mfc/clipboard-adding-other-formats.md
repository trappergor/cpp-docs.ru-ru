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
ms.openlocfilehash: 6f4e159cc1b6918843d4a164dcca88500eb7b038
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374606"
---
# <a name="clipboard-adding-other-formats"></a>Буфер обмена. Добавление других форматов

Эта тема объясняет, как расширить список поддерживаемых форматов, особенно для поддержки OLE. Тема [Clipboard: Копирование и вставки данных](../mfc/clipboard-copying-and-pasting-data.md) описывает минимальную реализацию, необходимую для поддержки копирования и вставки из Clipboard. Если это все, что вы реализуете, только форматы размещены на Clipboard **являются CF_METAFILEPICT,** **CF_EMBEDSOURCE,** **CF_OBJECTDESCRIPTOR,** и, возможно, **CF_LINKSOURCE**. Большинству приложений потребуется больше форматов на Clipboard, чем эти три.

## <a name="registering-custom-formats"></a><a name="_core_registering_custom_formats"></a>Регистрация пользовательских форматов

Чтобы создать свои собственные форматы, следуйте той же процедуре, что и при регистрации любого пользовательского формата Clipboard: передайте название формата функции **RegisterClipboardFormat** и используйте его значение возврата в качестве идентификатора формата.

## <a name="placing-formats-on-the-clipboard"></a><a name="_core_placing_formats_on_the_clipboard"></a>Размещение форматов на буфере обмена

Чтобы добавить больше форматов к тем, которые размещены на Clipboard, необходимо переопределить `OnGetClipboardData` функцию в классе, который вы получили из любого `COleClientItem` или `COleServerItem` (в зависимости от того, являются ли данные, которые будут скопированы, родными). В этой функции следует использовать следующую процедуру.

#### <a name="to-place-formats-on-the-clipboard"></a>Размещать форматы на Clipboard

1. Создание объекта `COleDataSource`.

1. Передайте этот источник данных функции, которая добавляет ваши родные `COleDataSource::CacheGlobalData`форматы данных в список поддерживаемых форматов, вызывая:

1. Добавьте стандартные `COleDataSource::CacheGlobalData` форматы, позвонив в каждый стандартный формат, который вы хотите поддержать.

Этот метод используется в программе mFC OLE образца `OnGetClipboardData` [HIERSVR](../overview/visual-cpp-samples.md) (изучить функцию члена класса **CServerItem).** Единственное отличие в этой выборке заключается в том, что третий этап не реализован, поскольку HIERSVR не поддерживает другие стандартные форматы.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Объекты данных OLE и источники данных и единая передача данных](../mfc/data-objects-and-data-sources-ole.md)

- [Перетаскивание OLE](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>См. также раздел

[Буфер обмена. Использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
