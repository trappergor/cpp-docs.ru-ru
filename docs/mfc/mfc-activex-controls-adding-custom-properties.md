---
title: "Элементы управления ActiveX MFC: Добавление пользовательских свойств | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f64154142c4c5f0fb3f24dc63120799132983880
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>Элементы управления ActiveX в MFC. Добавление пользовательских свойств
Пользовательские свойства отличаются от свойств хранения, что пользовательские свойства не реализованные `COleControl` класса. Пользовательское свойство используется для предоставления состояния или внешнего вида элемента управления ActiveX программисту, с помощью элемента управления.  
  
 В этой статье описывается добавление пользовательского свойства в элемент управления ActiveX, используя мастер добавления свойств и описываются изменения, полученный код. Ниже приведен список разделов.  
  
-   [С помощью мастера добавления свойства для добавления пользовательских свойств](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [Добавить свойство мастер изменения для пользовательских свойств](#_core_classwizard_changes_for_custom_properties)  
  
 Пользовательские свойства делятся на четыре вида реализация: переменной-члена, переменной-члена с уведомлением, методы Get и Set и параметризованные.  
  
-   Реализация переменной-члена  
  
     Эта реализация представляет состояние свойства в виде переменной-члена в классе элемента управления. Используйте реализацию переменной-члена, если не требуется знать, когда изменяется значение свойства. Три типа эта реализация создает наименьший объем код поддержки для свойства. Макрос записи карты распределения для реализации переменной члена — [DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property).  
  
-   Переменная-член с реализацией уведомления  
  
     Эта реализация состоит из переменной-члена и функции уведомления, созданные с помощью мастера добавления свойства. Функция уведомлений автоматически вызывается платформой, после изменения значения свойства. Использование переменной-члена с реализацией уведомления при необходимости получать уведомления, после изменения значения свойства. Эта реализация требует больше времени, так как он требует вызова функции. Макрос диспетчеризации карты для этой реализации является [DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify).  
  
-   Реализация методов get и Set  
  
     Эта реализация состоит из пары функций-членов в классе элемента управления. Реализация методов Get и Set автоматически вызывает этот член функции при запросе текущее значение свойства элемента управления пользователя, а функция-член набора при запросе пользователя элемента управления изменить свойство. Используйте эту реализацию, когда необходимо вычисления значения свойства во время выполнения проверки переданный пользователем элемента управления перед изменением свойства фактические значения или реализовывать тип свойства или записи — только для чтения. Макрос диспетчеризации карты для этой реализации является [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex). Следующий раздел: [с помощью мастера добавления свойства для добавления пользовательских свойств](#_core_using_classwizard_to_add_a_custom_property), использует пользовательское свойство CircleOffset для демонстрации этой реализации.  
  
-   Параметризованные реализации  
  
     Мастер добавления свойств поддерживается параметризованные реализации. Свойства с параметрами (иногда называется массива свойства) могут использоваться для доступа к набор значений через одно свойство элемента управления. Макрос диспетчеризации карты для этой реализации является `DISP_PROPERTY_PARAM`. Дополнительные сведения о реализации этого типа см. в разделе [реализации параметризованные свойства](../mfc/mfc-activex-controls-advanced-topics.md) в статье элементы управления ActiveX: Дополнительные разделы.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a>Используя мастер добавления свойства для добавления пользовательских свойств  
 Ниже показано, как добавить пользовательское свойство CircleOffset, который использует реализацию методов Get и Set. Пользовательское свойство CircleOffset позволяет пользователю элемента управления смещение круг в центре ограничивающего прямоугольника элемента управления. Процедура добавления пользовательских свойств с реализацией Кроме методов Get и Set очень похожа.  
  
 Эта процедура может также использоваться для других пользовательских свойств, которые нужно добавить. Замените на имя пользовательского свойства CircleOffset имя свойства и параметры.  
  
#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Чтобы добавить пользовательское свойство CircleOffset с помощью мастера добавления свойства  
  
1.  Загрузите проект элемента управления.  
  
2.  В представлении класса разверните узел библиотеки элемента управления.  
  
3.  Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.  
  
4.  В контекстном меню щелкните **добавить** и нажмите кнопку **добавить свойство**.  
  
     При этом откроется [мастер добавления свойств](../ide/names-add-property-wizard.md).  
  
5.  В **имя свойства** введите `CircleOffset`.  
  
6.  В поле **Тип реализации**выберите **Методы Get/Set**.  
  
7.  В **тип свойства** выберите **короткие**.  
  
8.  Введите уникальные имена для вашего функций Get и Set или примите имена по умолчанию.  
  
9. Нажмите кнопку **Готово**.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a>Добавить мастер изменения свойств для пользовательских свойств  
 При добавлении настраиваемого свойства CircleOffset, мастер добавления свойств вносит изменения в заголовке (. (H) и реализацию (. Файлы CPP) класса элемента управления.  
  
 Добавляются следующие строки. H-файл для объявления двух функций, вызванных `GetCircleOffset` и `SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 Следующая строка добавляется в элемент управления. IDL-файла:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 Эта строка назначает свойство CircleOffset с определенным номером код взят из метода положение в списке методов и свойств, мастер добавления свойств.  
  
 Кроме того, добавляется следующая строка карты распределения (в. CPP-файл класса элемента управления) для сопоставления свойства CircleOffset функции обработчика два элемента управления:  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 Наконец, реализации `GetCircleOffset` и `SetCircleOffset` функции добавляются в конец элемента управления. CPP-файл. В большинстве случаев предстоит изменить функцию Get для возврата значения свойства. Функция Set обычно содержит код, который должен быть выполнен до или после изменения свойств.  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 Обратите внимание, что мастер добавления свойств автоматически добавляет вызова, в [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), в теле функции набора. Вызов этой функции отмечает элемент управления, как измененный. Если элемент управления был изменен, его нового состояния будут сохранены при сохранении контейнера. Эта функция должна вызываться при каждом изменении значения свойства, сохраняются как часть постоянное состояние элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Элементы управления MFC ActiveX: свойства](../mfc/mfc-activex-controls-properties.md)   
 [Элементы управления MFC ActiveX: методы](../mfc/mfc-activex-controls-methods.md)   
 [Класс COleControl](../mfc/reference/colecontrol-class.md)