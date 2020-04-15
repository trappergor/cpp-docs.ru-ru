---
title: Объекты и источники данных. Манипуляция
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], manipulating
- data sources [MFC], data operations
- data sources [MFC], inserting data
- Clipboard [MFC], determining available formats
- OLE [MFC], data objects
- Clipboard [MFC], passing format information
- data sources [MFC], determining available formats
- delayed rendering [MFC]
- OLE [MFC], data sources
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
ms.openlocfilehash: a08b6ff274c73d301c156d65aa56fbecca49128c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370553"
---
# <a name="data-objects-and-data-sources-manipulation"></a>Объекты и источники данных. Манипуляция

После создания объекта данных или источника данных можно выполнить ряд общих операций на данных, таких как вставка и удаление данных, перечисление форматов, в которые входят данные, и многое другое. В этой статье описаны методы, необходимые для выполнения наиболее распространенных операций. Будут рассмотрены следующие задачи:

- [Включение данных в источник данных](#_core_inserting_data_into_a_data_source)

- [Определение форматов, доступных в объекте данных](#_core_determining_the_formats_available_in_a_data_object)

- [Извлечение данных из объекта данных](#_core_retrieving_data_from_a_data_object)

## <a name="inserting-data-into-a-data-source"></a><a name="_core_inserting_data_into_a_data_source"></a>Вставка данных в источник данных

Способ вставки данных в источник данных зависит от того, поставляются ли данные немедленно или по требованию и в какой среде они поставляются. Возможности таковы.

### <a name="supplying-data-immediately-immediate-rendering"></a>Немедленное предоставление данных (немедленная рендеринг)

- Позвоните `COleDataSource::CacheGlobalData` повторно для каждого формата Clipboard, в котором вы поставляете данные. Передайте использовать формат Clipboard, ручку памяти, содержащую данные, и, по желанию, структуру **FORMATETC,** описывающую данные.

     -или-

- Если вы хотите работать непосредственно со структурами `COleDataSource::CacheData` **STGMEDIUM,** вы звоните, а не `COleDataSource::CacheGlobalData` в варианте выше.

### <a name="supplying-data-on-demand-delayed-rendering"></a>Предоставление данных по запросу (Задержка рендеринга)

Это продвинутая тема.

- Позвоните `COleDataSource::DelayRenderData` повторно для каждого формата Clipboard, в котором вы поставляете данные. Передайте формат Clipboard для использования и, по желанию, структуру **FORMATETC,** описывающую данные. Когда данные запрашиваются, фреймворк `COleDataSource::OnRenderData`вызовет, который необходимо переопределить.

     -или-

- Если вы `CFile` используете объект для `COleDataSource::DelayRenderFileData` передачи `COleDataSource::DelayRenderData` данных, позвоните вместо предыдущего варианта. Когда данные запрашиваются, фреймворк `COleDataSource::OnRenderFileData`вызовет, который необходимо переопределить.

## <a name="determining-the-formats-available-in-a-data-object"></a><a name="_core_determining_the_formats_available_in_a_data_object"></a>Определение форматов, доступных в объекте данных

Прежде чем приложение позволяет пользователю вставить данные в него, он должен знать, если Есть форматы на Clipboard, что он может обрабатывать. Для этого приложение должно сделать следующее:

1. Создайте `COleDataObject` объект и структуру **FORMATETC.**

1. Вызовите функцию `AttachClipboard` члена объекта данных, чтобы связать объект данных с данными на Clipboard.

1. Выполните одно из следующих действий.

   - Позвоните в функцию `IsDataAvailable` члена объекта данных, если вам нужен только один или два формата. Это сэкономит вам время в тех случаях, когда данные на Clipboard поддерживают значительно больше форматов, чем ваше приложение.

     \-или-

   - Вызовите функцию `BeginEnumFormats` члена объекта данных, чтобы начать перечисление форматов, доступных на Clipboard. Затем `GetNextFormat` позвоните до тех пор, пока Clipboard не вернет формат, который поддерживает приложение, или больше нет форматов.

Если вы используете **ON_UPDATE_COMMAND_UI,** теперь вы можете включить пасту и, возможно, вставить специальные элементы в меню Edit. Для этого позвоните `CMenu::EnableMenuItem` `CCmdUI::Enable`либо или . Для получения дополнительной информации о том, что контейнерные приложения должны делать с пунктами меню и когда, [см. Меню и Ресурсы: КонтейнерНые дополнения](../mfc/menus-and-resources-container-additions.md).

## <a name="retrieving-data-from-a-data-object"></a><a name="_core_retrieving_data_from_a_data_object"></a>Извлечение данных из объекта данных

После того как вы определились с форматом данных, остается только извлечение данных из объекта данных. Для этого пользователь решает, куда разместить данные, и приложение вызывает соответствующую функцию. Данные будут доступны в одном из следующих носителей:

|Средний|Функция вызова|
|------------|----------------------|
|Глобальная`HGLOBAL`память ( )|`COleDataObject::GetGlobalData`|
|Файл`CFile`( )|`COleDataObject::GetFileData`|
|Структура **STGMEDIUM** ()`IStorage`|`COleDataObject::GetData`|

Как правило, среда будет указана вместе с форматом Clipboard. Например, **CF_EMBEDDEDSTRUCT** объект всегда `IStorage` находится в среде, требующей структуры **STGMEDIUM.** Таким образом, `GetData` вы бы использовать, потому что это единственная из этих функций, которые могут принять структуру **STGMEDIUM.**

В случаях, когда формат Clipboard `HGLOBAL` находится в среде `CFile` `IStream` или среде, фреймворк может предоставить указатель, который ссылается на данные. Приложение может использовать считываемые файлы, чтобы получить данные во многом так же, как это может импортировать данные из файла. По сути, это интерфейс клиентской `OnRenderData` `OnRenderFileData` стороны к и процедуры в источнике данных.

Теперь пользователь может вставлять данные в документ, как и для любых других данных в том же формате.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Перетащите и падение](../mfc/drag-and-drop-ole.md)

- [Буфер обмена](../mfc/clipboard.md)

## <a name="see-also"></a>См. также раздел

[Объекты и источники данных (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[Класс COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
[Класс COleDataSource](../mfc/reference/coledatasource-class.md)
