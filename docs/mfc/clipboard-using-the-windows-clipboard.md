---
title: Буфер обмена. Использование буфера обмена Windows
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
ms.openlocfilehash: 1b11bfe18443858de0dd7032f72fecadb1d6ebdd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626040"
---
# <a name="clipboard-using-the-windows-clipboard"></a>Буфер обмена. Использование буфера обмена Windows

В этом разделе описывается, как использовать стандартный API буфера обмена Windows в приложении MFC.

Большинство приложений для Windows поддерживают Вырезание или копирование данных в буфер обмена Windows и вставляя данные из буфера обмена. Форматы данных буфера обмена могут различаться в разных приложениях. Платформа поддерживает только ограниченное число форматов буфера обмена для ограниченного числа классов. Вы обычно реализуете команды, связанные с буфером обмена (вырезание, копирование и вставка), в меню Правка для представления. Библиотека классов определяет идентификаторы команд для следующих команд: **ID_EDIT_CUT**, **ID_EDIT_COPY**и **ID_EDIT_PASTE**. Также определяются сообщения командной строки.

[Сообщения и команды в платформе](messages-and-commands-in-the-framework.md) поясняют, как управлять командами меню в приложении путем сопоставления команды меню с функцией обработчика. Пока приложение не определяет функции обработчика для команд буфера обмена в меню Правка, они остаются отключенными. Чтобы написать функции обработчика для команд Cut и Copy, реализуйте выбор в приложении. Чтобы написать функцию обработчика для команды вставки, запросите буфер обмена, чтобы узнать, содержит ли он данные в формате, который может принимать приложение. Например, чтобы включить команду Copy, вы можете написать обработчик примерно следующего вида:

[!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]

Команды вырезания, копирования и вставки имеют смысл только в определенных контекстах. Команды "вырезать" и "Копировать" должны быть включены только в том случае, если что-то выбрано, а команда вставить только в буфер обмена. Это поведение можно предоставить, определив функции обработчика обновлений, которые включают или отключают эти команды в зависимости от контекста. Дополнительные сведения см. [в разделе Обновление объектов пользовательского интерфейса](how-to-update-user-interface-objects.md).

Библиотека Microsoft Foundation Class обеспечивает поддержку буфера обмена для редактирования текста с помощью `CEdit` классов и `CEditView` . Классы OLE также упрощают реализацию операций с буфером обмена, использующих элементы OLE. Дополнительные сведения о классах OLE см. [в разделе буфер обмена. Использование механизма буфера обмена OLE](clipboard-using-the-ole-clipboard-mechanism.md).

Реализация других команд меню "Правка", таких как "отменить" (**ID_EDIT_UNDO**) и "повторить" (**ID_EDIT_REDO**), также остается ненужной. Если приложение не поддерживает эти команды, их можно легко удалить из файла ресурсов с помощью Visual C++ редакторов ресурсов.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Копирование и вставка данных](clipboard-copying-and-pasting-data.md)

- [Использование механизма буфера обмена OLE](clipboard-using-the-ole-clipboard-mechanism.md)

## <a name="see-also"></a>См. также раздел

[Буфер обмена](clipboard.md)
