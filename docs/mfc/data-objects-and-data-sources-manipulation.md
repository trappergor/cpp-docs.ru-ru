---
title: 'Объекты и источники данных: манипуляции | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f276e85be33f3042b19ab7dc6158a4e9f856fb2e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929865"
---
# <a name="data-objects-and-data-sources-manipulation"></a>Объекты и источники данных. Манипуляция
После создания объекта данных или источник данных можно выполнить ряд общих операций на данные, такие как вставка и удаление данных, перечисление форматы файлов, которые данные находятся в, и многое другое. В этой статье описаны методы, необходимые для выполнения наиболее часто выполняемые операции. Ниже приведен список разделов.  
  
-   [Вставка данных в источник данных](#_core_inserting_data_into_a_data_source)  
  
-   [Определение форматов, доступные в объекте данных](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [Извлечение данных из объекта данных](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a> Вставка данных в источник данных  
 Способ вставки данных в источник данных зависит ли данные передаются непосредственно или по требованию и на носителе, для которого предоставляется. Возможные значения — следующим образом.  
  
### <a name="supplying-data-immediately-immediate-rendering"></a>Предоставление данных немедленно (немедленно подготовки отчетов)  
  
-   Вызовите `COleDataSource::CacheGlobalData` несколько раз для каждого формата буфера обмена, в котором указываются данные. Передайте формат буфера обмена для использования, дескриптор памяти, содержащую данные, возможно, **FORMATETC** структуры, описывающие данные.  
  
     - или -  
  
-   Если требуется работать непосредственно с **STGMEDIUM** структур, вызовите `COleDataSource::CacheData` вместо `COleDataSource::CacheGlobalData` в указанных выше параметров.  
  
### <a name="supplying-data-on-demand-delayed-rendering"></a>Предоставляет данные по требованию (отложенная отрисовка)  
 Это довольно сложная тема.  
  
-   Вызовите `COleDataSource::DelayRenderData` несколько раз для каждого формата буфера обмена, в котором указываются данные. Передайте формат буфера обмена для использования, возможно, **FORMATETC** структуры, описывающие данные. При запросе данных платформа вызывает `COleDataSource::OnRenderData`, который необходимо переопределить.  
  
     - или -  
  
-   Если вы используете `CFile` объект в качестве источника данных, вызовите `COleDataSource::DelayRenderFileData` вместо `COleDataSource::DelayRenderData` в предыдущем варианте. При запросе данных платформа вызывает `COleDataSource::OnRenderFileData`, который необходимо переопределить.  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> Определение форматов, доступные в объекте данных  
 Прежде чем приложение позволяет пользователю вставлять данные в него, необходимо знать, если существует форматов в буфере обмена, он может обрабатывать. Для этого приложения они должны сделать следующее:  
  
1.  Создание `COleDataObject` объекта и **FORMATETC** структуры.  
  
2.  Вызов объекта данных `AttachClipboard` функции-члена для связать объект данных с данными в буфере обмена.  
  
3.  Выполните одно из следующих действий.  
  
    -   Вызов объекта данных `IsDataAvailable` требуется функция-член, если имеется только один или два форматах. Это позволит сэкономить время в случаях, когда данные в буфер обмена поддерживает форматы значительно больше, чем приложения.  
  
         - или -  
  
    -   Вызов объекта данных `BeginEnumFormats` функции-члена начинается перечисление форматы, доступные в буфере обмена. Затем вызовите `GetNextFormat` до возврата в буфер обмена поддерживает формат приложения или что отсутствуют дополнительные форматы.  
  
 Если вы используете **ON_UPDATE_COMMAND_UI**, теперь можно включить вставить и, возможно, Специальная вставка элементов в меню "Правка". Чтобы сделать это, вызовите `CMenu::EnableMenuItem` или `CCmdUI::Enable`. Дополнительные сведения о какой контейнера приложений следует делать с пунктов меню и ответ, [меню и ресурсы: добавление контейнеров](../mfc/menus-and-resources-container-additions.md).  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a> Извлечение данных из объекта данных  
 После выбора формата данных, остается для извлечения данных из объекта данных. Чтобы сделать это, пользователь решает, куда поместить данные, и приложение вызывает соответствующую функцию. Данные будут доступны в одном из следующих носители:  
  
|Средняя|Функция, вызываемая|  
|------------|----------------------|  
|Глобальная память (`HGLOBAL`)|`COleDataObject::GetGlobalData`|  
|Файл (`CFile`)|`COleDataObject::GetFileData`|  
|**STGMEDIUM** структуры (`IStorage`)|`COleDataObject::GetData`|  
  
 Как правило носитель должен указываться вместе с его формат буфера обмена. Например **CF_EMBEDDEDSTRUCT** объект всегда находится в `IStorage` носитель, который требуется **STGMEDIUM** структуры. Таким образом, используется `GetData` так как это только один из этих функций, которые могут принимать **STGMEDIUM** структуры.  
  
 В случае если формат буфера обмена в `IStream` или `HGLOBAL` средний, можно предоставить платформа `CFile` указатель, который обращается к данным. Затем приложение может использовать для получения данных во многом так же, как он может импортировать данные из файла чтения файлов. По сути, это клиентский интерфейс для `OnRenderData` и `OnRenderFileData` подпрограммы в источнике данных.  
  
 Пользователь может теперь вставки данных в документ так же, как для любых данных, в том же формате.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Перетаскивание](../mfc/drag-and-drop-ole.md)  
  
-   [Буфер обмена](../mfc/clipboard.md)  
  
## <a name="see-also"></a>См. также  
 [Объекты и источники данных (OLE)](../mfc/data-objects-and-data-sources-ole.md)   
 [Класс COleDataObject](../mfc/reference/coledataobject-class.md)   
 [Класс COleDataSource](../mfc/reference/coledatasource-class.md)
