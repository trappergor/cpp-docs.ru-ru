---
title: Элементы управления ActiveX в MFC. Реализация расширенных свойств
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: d4f1265e6540e9f84bdb680e7948a4e308d31bb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364653"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>Элементы управления ActiveX в MFC. Реализация расширенных свойств

В этой статье описаны темы, связанные с реализацией расширенных свойств в элементе управления ActiveX.

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

- [Свойства только для чтения и записи](#_core_read2donly_and_write2donly_properties)

- [Возвращение кодов ошибок из свойства](#_core_returning_error_codes_from_a_property)

## <a name="read-only-and-write-only-properties"></a><a name="_core_read2donly_and_write2donly_properties"></a>Только читать и писать только свойства

Мастер свойств Добавления предоставляет быстрый и простой способ реализации свойств только для чтения или записи только для управления.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>Реализация свойства только для чтения или записи

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. Из меню ярлыка, нажмите **Добавить,** а затем нажмите **Добавить свойство**.

   Это открывает [Мастер свойств добавления.](../ide/names-add-property-wizard.md)

1. В поле **имени свойства** введите имя вашего имущества.

1. В поле **Тип реализации**выберите **Методы Get/Set**.

1. В поле **Типа свойства** выберите правильный тип для свойства.

1. Если вы хотите свойство только для чтения, очистите имя функции Set. Если вы хотите только для записи свойство, очистить название функции Get.

1. Нажмите кнопку **Готово**.

При этом мастер свойств добавить свойств `SetNotSupported` вставляет функцию или `GetNotSupported` в вход на карту отправки вместо обычной функции Set или Get.

Если вы хотите изменить существующее свойство, чтобы быть прочитанном или только для записи, вы можете отредактировать карту отправки вручную и удалить ненужный набор или получить функцию из класса управления.

Если вы хотите, чтобы свойство было условно прочитано только или только для записи (например, только при работе элемента управления `SetNotSupported` в `GetNotSupported` определенном режиме), вы можете предоставить функцию Set or Get, как обычно, и вызвать или функцию, где это уместно. Пример:

[!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

Этот образец `SetNotSupported` кода `m_bReadOnlyMode` вызывает, если член данных **является правдой**. Если **FALSE**, то свойство устанавливается на новое значение.

## <a name="returning-error-codes-from-a-property"></a><a name="_core_returning_error_codes_from_a_property"></a>Возвращающиеся коды ошибки из свойства

Чтобы указать, что ошибка произошла при попытке получить `COleControl::ThrowError` или установить свойство, используйте функцию, которая принимает SCODE (код статуса) в качестве параметра. Вы можете использовать предопределенный SCODE или определить один из ваших собственных. Список предопределенных СКОДЕ и инструкций по определению [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) пользовательских СКОДЕ см.

Функции помощника существуют для наиболее распространенных предопределенных SCODEs, таких как [COleControl::SetNotSupported,](../mfc/reference/colecontrol-class.md#setnotsupported) [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), и [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

> [!NOTE]
> `ThrowError`предназначен для использования только в качестве средства возврата ошибки из функции Get или Set свойства или метода автоматизации. Это единственные случаи, когда соответствующий обработчик исключений будет присутствовать в стеке.

Для получения дополнительной информации об исключениях в других областях кода [см. COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) и раздел [Обработка ошибок в вашем ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) в статье ActiveX Controls: Расширенные темы.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Свойства](../mfc/mfc-activex-controls-properties.md)<br/>
[Элементы ActiveX в MFC. Методы](../mfc/mfc-activex-controls-methods.md)<br/>
[Класс COleControl](../mfc/reference/colecontrol-class.md)
