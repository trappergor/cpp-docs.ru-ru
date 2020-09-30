---
title: Элементы управления ActiveX в MFC. Реализация расширенных свойств
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: 017959c5809d324af6ab13247fd093a6df280dab
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502200"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>Элементы управления ActiveX в MFC. Реализация расширенных свойств

В этой статье описываются темы, связанные с реализацией дополнительных свойств в элементе управления ActiveX.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которую не следует использовать для новой разработки. Дополнительные сведения о современных технологиях, которые заменяют ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

- [Свойства только для чтения и только для записи](#_core_read2donly_and_write2donly_properties)

- [Возвращение кодов ошибок из свойства](#_core_returning_error_codes_from_a_property)

## <a name="read-only-and-write-only-properties"></a><a name="_core_read2donly_and_write2donly_properties"></a> Свойства только для чтения и только для записи

Мастер добавления свойств предоставляет быстрый и простой способ реализации свойств элемента управления только для чтения или только для записи.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>Реализация свойства только для чтения или только для записи

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. В контекстном меню выберите **Добавить** , а затем — **Добавить свойство**.

   Откроется [Мастер добавления свойств](../ide/adding-a-property-visual-cpp.md#names-add-property-wizard).

1. В поле **имя свойства** введите имя свойства.

1. В поле **Тип реализации**выберите **Методы Get/Set**.

1. В поле **тип свойства** выберите правильный тип для свойства.

1. Если требуется доступное только для чтения свойство, очистите имя функции Set. Если требуется свойство только для записи, очистите имя функции Get.

1. Нажмите кнопку **Готово**.

После этого мастер добавления свойств вставляет функцию `SetNotSupported` или `GetNotSupported` в запись "Отправка схемы" вместо обычного набора или функции "получить".

Если вы хотите изменить существующее свойство так, чтобы оно было доступно только для чтения или только для записи, можно изменить карту диспетчеризации вручную и удалить ненужные функции Set или Get из класса Control.

Если требуется, чтобы свойство было доступно только для чтения или только для записи (например, только если элемент управления работает в определенном режиме), можно предоставить функцию Set или Get как нормальную и вызвать `SetNotSupported` `GetNotSupported` функцию или там, где это уместно. Пример:

[!code-cpp[NVC_MFC_AxUI#29](codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

Этот пример кода вызывает, `SetNotSupported` Если `m_bReadOnlyMode` элемент данных имеет **значение true**. Если **значение равно false**, то свойству присваивается новое значение.

## <a name="returning-error-codes-from-a-property"></a><a name="_core_returning_error_codes_from_a_property"></a> Возвращение кодов ошибок из свойства

Чтобы указать, что при попытке получения или задания свойства произошла ошибка, используйте `COleControl::ThrowError` функцию, которая принимает SCODE (код состояния) в качестве параметра. Вы можете использовать предопределенный SCODE или определить один из них. Список стандартных Скодес и инструкции по определению пользовательских Скодес см. в статье [Обработка ошибок в элементе управления ActiveX](mfc-activex-controls-advanced-topics.md) статьи элементы ActiveX: дополнительные разделы.

Вспомогательные функции существуют для наиболее распространенных предопределенных Скодес, таких как [COleControl:: сетнотсуппортед](reference/colecontrol-class.md#setnotsupported), [COleControl:: жетнотсуппортед](reference/colecontrol-class.md#getnotsupported)и [COleControl:: сетнотпермиттед](reference/colecontrol-class.md#setnotpermitted).

> [!NOTE]
> `ThrowError` предназначен для использования только в качестве способа возвращения ошибки из функции Get или Set свойства или метода автоматизации. Это единственный раз, когда в стеке будет присутствовать соответствующий обработчик исключений.

Дополнительные сведения о сообщениях об исключениях в других областях кода см. в разделах [COleControl:: фириррор](reference/colecontrol-class.md#fireerror) и [Обработка ошибок в элементе управления ActiveX](mfc-activex-controls-advanced-topics.md) статьи элементы управления ActiveX: дополнительные разделы.

## <a name="see-also"></a>См. также

[Элементы управления ActiveX в MFC](mfc-activex-controls.md)<br/>
[Элементы управления ActiveX в MFC: свойства](mfc-activex-controls-properties.md)<br/>
[Элементы управления ActiveX в MFC: методы](mfc-activex-controls-methods.md)<br/>
[Класс COleControl](reference/colecontrol-class.md)
