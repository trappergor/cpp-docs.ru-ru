---
title: Классы общих диалоговых окон OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
ms.openlocfilehash: 1854d19c540f5e3e64b47786f465a05213eced86
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617795"
---
# <a name="ole-common-dialog-classes"></a>Классы общих диалоговых окон OLE

Эти классы обрабатывали общие задачи OLE, реализуя ряд стандартных диалоговых окон OLE. Они также предоставляют единообразный пользовательский интерфейс для функций OLE.

[COleDialog](reference/coledialog-class.md)<br/>
Используется платформой для хранения общих реализаций для всех диалоговых окон OLE. Все классы диалоговых окон в категории пользовательского интерфейса являются производными от этого базового класса. `COleDialog`не может использоваться напрямую.

[COleInsertDialog](reference/coleinsertdialog-class.md)<br/>
Отображает диалоговое окно Вставка объекта — стандартный пользовательский интерфейс для вставки новых связанных или внедренных элементов OLE.

[COlePasteSpecialDialog](reference/colepastespecialdialog-class.md)<br/>
Отображает диалоговое окно Специальная вставка — стандартный пользовательский интерфейс для реализации команды изменить вставку специальной программы.

[COleLinksDialog](reference/colelinksdialog-class.md)<br/>
Отображает диалоговое окно изменение ссылок — стандартный пользовательский интерфейс для изменения сведений о связанных элементах.

[COleChangeIconDialog](reference/colechangeicondialog-class.md)<br/>
Отображает диалоговое окно Изменение значка — стандартный пользовательский интерфейс для изменения значка, связанного с внедренным или связанным элементом OLE.

[COleConvertDialog](reference/coleconvertdialog-class.md)<br/>
Отображает диалоговое окно Преобразование — стандартный пользовательский интерфейс для преобразования элементов OLE из одного типа в другой.

[COlePropertiesDialog](reference/colepropertiesdialog-class.md)<br/>
Инкапсулирует диалоговое окно Общие свойства OLE Windows. Общие диалоговые окна свойств OLE предоставляют простой способ просмотра и изменения свойств элемента документа OLE способом, согласованным со стандартами Windows.

[COleUpdateDialog](reference/coleupdatedialog-class.md)<br/>
Отображает диалоговое окно Обновление — стандартный пользовательский интерфейс для обновления всех ссылок в документе. Диалоговое окно содержит индикатор выполнения, указывающий, как завершить процедуру обновления до завершения.

[COleChangeSourceDialog](reference/colechangesourcedialog-class.md)<br/>
Отображает диалоговое окно Изменение источника — стандартный пользовательский интерфейс для изменения назначения или источника ссылки.

[COleBusyDialog](reference/colebusydialog-class.md)<br/>
Отображает диалоговые окна сервер занят и сервер не отвечает — стандартный пользовательский интерфейс для обработки вызовов занятых приложений. Обычно автоматически отображается `COleMessageFilter` реализацией.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
