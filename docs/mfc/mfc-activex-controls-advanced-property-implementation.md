---
title: 'Элементы управления MFC ActiveX: Реализация свойств Дополнительные | Документация Майкрософт'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 084ef5e2a6173340d33baea94bd1e5c5f14bff9b
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204487"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>Элементы управления ActiveX в MFC. Реализация расширенных свойств

В этой статье описываются разделы, относящиеся к реализации дополнительных свойств в элементе управления ActiveX.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

- [Свойства только для чтения и только для записи](#_core_read2donly_and_write2donly_properties)

- [Возврат кодов ошибок из свойства](#_core_returning_error_codes_from_a_property)

##  <a name="_core_read2donly_and_write2donly_properties"></a> Свойства только для чтения и только для записи

Мастер добавления свойств предоставляет быстрый и простой способ реализовать только для чтения или только для записи свойства для элемента управления.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>Реализация свойства только для чтения или только для записи

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. В контекстном меню, щелкните **добавить** и нажмите кнопку **добавить свойство**.

   Откроется [мастер добавления свойств](../ide/names-add-property-wizard.md).

1. В **имя свойства** введите имя свойства.

1. В поле **Тип реализации**выберите **Методы Get/Set**.

1. В **тип свойства** выберите соответствующего типа для свойства.

1. Если вы хотите только для чтения, снимите имя функции Set. Свойство только для записи, снимите имя функции Get.

9. Нажмите кнопку **Готово**.

При этом мастер добавления свойств вставляет функцию `SetNotSupported` или `GetNotSupported` в записи карты диспетчеризации вместо обычной установки или получения функции.

Если вы хотите изменить существующее свойство только для чтения или только для записи, можно вручную изменить диспетчерскую карту и удалить ненужные функции Set или Get из класса control.

Если требуется, чтобы свойства как условно доступный только для чтения или только для записи (например, только в том случае, когда элемент управления работает в определенном режиме), можно задать функцию Set или Get, в обычном режиме и вызвать `SetNotSupported` или `GetNotSupported` функционировать, если это уместно. Пример:

[!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

Этот пример кода вызывает `SetNotSupported` Если `m_bReadOnlyMode` член данных является **TRUE**. Если **FALSE**, то свойство присваивается новое значение.

##  <a name="_core_returning_error_codes_from_a_property"></a> Возврат кодов ошибок из свойства

Чтобы указать, что произошла ошибка при попытке получить или задать свойство, используйте `COleControl::ThrowError` функцию, которая принимает SCODE (код состояния) как параметр. Можно использовать предопределенные SCODE или определить один из ваших собственных. Список предварительно определенных SCODEs и инструкции по созданию пользовательских SCODEs, см. в разделе [обработка ошибок в ваш элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX статьи: Дополнительные разделы.

Вспомогательные функции существуют для самых распространенных стандартными SCODEs, такими как [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), и [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

> [!NOTE]
>  `ThrowError` предназначен для использования только с точки зрения сообщение об ошибке из внутри свойства Get или Set функция или метод автоматизации. Это только те представления времени, которые будут соответствующему обработчику исключений в стеке.

Дополнительные сведения о reporting исключения в других областях кода, см. в разделе [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) и разделе [обработка ошибок в ваш элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в этой статье элементы управления ActiveX: Дополнительно Разделы.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Свойства](../mfc/mfc-activex-controls-properties.md)<br/>
[Элементы ActiveX в MFC. Методы](../mfc/mfc-activex-controls-methods.md)<br/>
[Класс COleControl](../mfc/reference/colecontrol-class.md)
