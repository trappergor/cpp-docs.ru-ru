---
title: Буфер обмена. Копирование и вставка данных
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
ms.openlocfilehash: 74348dd3e790cceada9aafd718464694997316ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374572"
---
# <a name="clipboard-copying-and-pasting-data"></a>Буфер обмена. Копирование и вставка данных

Эта тема описывает минимальную работу, необходимую для реализации копирования и вставки из Clipboard в приложении OLE. Рекомендуется, чтобы вы прочитали [данные объектов и источников данных (OLE)](../mfc/data-objects-and-data-sources-ole.md) темы, прежде чем продолжить.

Прежде чем реализовать копирование или вставку, необходимо сначала предоставить функции для обработки вариантов copy, Cut и Paste в меню Edit.

## <a name="copying-or-cutting-data"></a><a name="_core_copying_or_cutting_data"></a>Копирование или сокращение данных

#### <a name="to-copy-data-to-the-clipboard"></a>Копирование данных в Clipboard

1. Определите, являются ли данные, которые должны быть скопированы, родными данными или встроенным или связанным элементом.

   - Если данные встроены или связаны, `COleClientItem` получите указатель на выбранный объект.

   - Если данные являются родными, а приложение — сервером, создайте новый объект, полученный из `COleServerItem` содержащих выбранные данные. В противном `COleDataSource` случае создайте объект для данных.

1. Вызовите функцию `CopyToClipboard` члена выбранного элемента.

1. Если пользователь выбрал операцию Cut вместо операции Copy, удалите выбранные данные из приложения.

Чтобы увидеть пример этой последовательности, `OnEditCut` см. `OnEditCopy` [OCLIENT](../overview/visual-cpp-samples.md) [HIERSVR](../overview/visual-cpp-samples.md) Обратите внимание, что эти образцы сохраняют указатель на выбранные в настоящее время данные, поэтому шаг 1 уже завершен.

## <a name="pasting-data"></a><a name="_core_pasting_data"></a>Данные вставки

Вставить данные сложнее, чем копировать, потому что вам нужно выбрать формат для использования в вставке данных в приложение.

#### <a name="to-paste-data-from-the-clipboard"></a>Для вставки данных из Clipboard

1. В классе представления `OnEditPaste` реализация для обработки пользователей, выбирающих опцию Paste из меню Edit.

1. В `OnEditPaste` функции создайте `COleDataObject` объект `AttachClipboard` и позвоните его функции-члена, чтобы связать этот объект с данными на Clipboard.

1. Позвоните, `COleDataObject::IsDataAvailable` чтобы проверить, доступен ли определенный формат.

   Кроме того, вы `COleDataObject::BeginEnumFormats` можете использовать для поиска других форматов, пока вы не найдете один наиболее подходящий для вашего приложения.

1. Выполните пасту формата.

Например, как это работает, см. реализацию функций `OnEditPaste` участника в классах представления, определенных в примерных программах MFC OLE [OCLIENT](../overview/visual-cpp-samples.md) и [HIERSVR.](../overview/visual-cpp-samples.md)

> [!TIP]
> Основным преимуществом разделения операции пасты на свою собственную функцию является то, что один и тот же код пасты может быть использован при удалении данных в приложении во время операции перетаскивания. Как и в OCLIENT и `OnDrop` HIERSVR, ваша функция также может вызывать, `DoPasteItem`повторно использовать код, написанный для реализации операций вставить.

Для обработки пасты Специальный вариант в меню [Dialog Boxes in OLE](../mfc/dialog-boxes-in-ole.md)edit, см.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Добавление других форматов](../mfc/clipboard-adding-other-formats.md)

- [Объекты данных OLE и источники данных и единая передача данных](../mfc/data-objects-and-data-sources-ole.md)

- [Перетаскивание OLE](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>См. также раздел

[Буфер обмена. Использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
