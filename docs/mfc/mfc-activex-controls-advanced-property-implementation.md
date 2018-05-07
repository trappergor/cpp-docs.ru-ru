---
title: 'Элементы управления MFC ActiveX: Реализация свойств Дополнительные | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 97b6bbcbcf226d343d8b3cb51f110442e133a379
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>Элементы управления ActiveX в MFC. Реализация расширенных свойств
В этой статье описываются разделы, относящиеся к реализации дополнительных свойств в элементе управления ActiveX.  
  
-   [Свойства только для чтения и только для записи](#_core_read2donly_and_write2donly_properties)  
  
-   [Возврат кодов ошибок из свойства](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> Свойства только для чтения и только для записи  
 Мастер добавления свойств предоставляет быстрый и простой способ реализации свойств только для чтения или только для записи для элемента управления.  
  
#### <a name="to-implement-a-read-only-or-write-only-property"></a>Реализация свойства только для чтения или только для записи  
  
1.  Загрузите проект элемента управления.  
  
2.  В представлении класса разверните узел библиотеки элемента управления.  
  
3.  Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.  
  
4.  В контекстном меню щелкните **добавить** и нажмите кнопку **добавить свойство**.  
  
     При этом откроется [мастер добавления свойств](../ide/names-add-property-wizard.md).  
  
5.  В **имя свойства** введите имя свойства.  
  
6.  В поле **Тип реализации**выберите **Методы Get/Set**.  
  
7.  В **тип свойства** выберите правильный тип свойства.  
  
8.  Если требуется только для чтения, снимите имя набора функции. Если требуется, чтобы свойство только для записи, снимите имя функции Get.  
  
9. Нажмите кнопку **Готово**.  
  
 При этом мастер добавления свойств вставляет функцию `SetNotSupported` или `GetNotSupported` в записи карты диспетчеризации вместо обычной задать или получить функция.  
  
 Если вы хотите изменить существующее свойство только для чтения или только для записи, можно вручную изменить карту распределения и удалите ненужные функции Set или Get из класса элемента управления.  
  
 Если требуется, чтобы свойство было условно только для чтения или только для записи (например, только в том случае, когда элемент управления работает в определенном режиме), можно задать функцию Set или Get в обычном режиме и вызвать `SetNotSupported` или `GetNotSupported` функционировать, если это уместно. Например:  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 Этот пример кода вызывает `SetNotSupported` Если `m_bReadOnlyMode` член данных — **TRUE**. Если **FALSE**, то свойство задается новое значение.  
  
##  <a name="_core_returning_error_codes_from_a_property"></a> Возврат кодов ошибок из свойства  
 Чтобы показать, что произошла ошибка при попытке получить или задать свойство, используйте `COleControl::ThrowError` функцию, которая принимает `SCODE` (код состояния) как параметр. Можно использовать предварительно определенную `SCODE` или определить один из собственных. Список стандартных `SCODE`s и инструкции по созданию пользовательских `SCODE`s, в разделе [обработка ошибок в свой элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX статьи: Дополнительные разделы.  
  
 Существуют вспомогательные функции для наиболее частых предопределенные `SCODE`s, таких как [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), и [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
> [!NOTE]
>  `ThrowError` предназначены для использования только с точки зрения возврат из-за ошибки в свойство Get или Set функцию или метод автоматизации. Это только представляют время, которые будут подходящего обработчика исключений в стеке.  
  
 Дополнительные сведения об отчетности исключения в другие области кода см. в разделе [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) и разделе [обработка ошибок в свой элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в статье элементы управления ActiveX: Дополнительно Разделы.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Элементы управления MFC ActiveX: свойства](../mfc/mfc-activex-controls-properties.md)   
 [Элементы управления MFC ActiveX: методы](../mfc/mfc-activex-controls-methods.md)   
 [Класс COleControl](../mfc/reference/colecontrol-class.md)
