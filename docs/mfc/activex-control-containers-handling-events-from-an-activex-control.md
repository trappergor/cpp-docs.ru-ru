---
title: "Контейнеры элементов управления ActiveX: Обработка событий из элемента управления ActiveX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 3903be230f130aeaeb1953faf73a0c8af4c3492f
ms.openlocfilehash: a8fb283d8b5b8afbf3b06e27495ccc957e0099ad
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>Контейнеры элементов управления ActiveX. Обработка событий из элемента управления ActiveX
В этой статье рассматриваются в окне «Свойства» для установки обработчиков событий для элементов управления ActiveX в контейнере элементов управления ActiveX. Обработчики событий позволяют получать уведомления об определенных событиях (из элемента управления), а также выполнять некоторые действия в ответ. Это уведомление вызывается событие «запуск».  
  
> [!NOTE]
>  В этой статье используется на базе диалогового окна проекта элемента управления ActiveX контейнер с именем контейнера и внедренный элемент управления с именем Circ в качестве примеров в процедурах и кода.  
  
 С помощью "события" окна "Свойства", можно создать сопоставление событий, которые могут возникнуть в приложение контейнера элемента управления ActiveX. Эта схема, называемая «картой приемника событий,'' создается и сохраняется в Visual C++ при добавлении обработчиков событий в класс контейнера элемента управления. Каждый обработчик событий реализуется с помощью записи карты, определенное событие сопоставляется функции-члена обработчик событий контейнера. Эта функция обработчик событий вызывается при возникновении указанного события элемента управления ActiveX для объекта.  
  
 Дополнительные сведения о схемы приемников событий см. в разделе [схемы приемников событий](../mfc/reference/event-sink-maps.md) в *Справочник по библиотеке классов*.  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a>Изменения обработчика событий в проект  
 При использовании окна «Свойства» для добавления обработчиков событий, картой приемника событий объявлен и определен в проекте. Следующие инструкции, добавляются к элементу управления. CPP-файл при первом добавлении обработчика событий. Этот код объявляет картой приемника событий для класса диалогового окна (в данном случае `CContainerDlg`):  
  
 [!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]  
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]  
  
 При использовании окна «Свойства» для добавления событий событие сопоставить запись (`ON_EVENT`) добавляется к схеме событий приемника и обработчик событий функция будет добавлена реализация контейнера (. Файл CPP).  
  
 В следующем примере объявляется обработчик событий, называемый `OnClickInCircCtrl`, для управления Circ **ClickIn** событий:  
  
 [!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]  
  
 Кроме того, добавляется следующий шаблон `CContainerDlg` реализацию класса (. Файл .cpp) для функции-члена обработчика событий:  
  
 [!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]  
  
 Дополнительные сведения о макросы приемника событий см. в разделе [схемы приемников событий](../mfc/reference/event-sink-maps.md) в *Справочник по библиотеке классов*.  
  
#### <a name="to-create-an-event-handler-function"></a>Чтобы создать функцию обработчика событий  
  
1.  Представление классов выберите класс диалогового окна, содержащей элемент управления ActiveX. В этом примере используется `CContainerDlg`.  
  
2.  В окне «Свойства» щелкните **события** кнопки.  
  
3.  В окне «Свойства» выберите идентификатор элемента управления внедренный элемент управления ActiveX. В этом примере используется `IDC_CIRCCTRL1`.  
  
     Окна «Свойства» отображается список событий, которые могут запускаться внедренного элемента управления ActiveX. Любую функцию-член отображается полужирным шрифтом, уже имеет функции обработчика, назначенного ей.  
  
4.  Выберите событие, класс диалогового окна для обработки. В этом примере выберите **щелкните**.  
  
5.  В раскрывающемся списке справа выберите ** \<Добавить > ClickCircctrl1**.  
  
6.  Дважды щелкните новую функцию обработчика из представления классов, чтобы перейти к коду обработчика событий в реализации (. Файл CPP) `CContainerDlg`.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)


