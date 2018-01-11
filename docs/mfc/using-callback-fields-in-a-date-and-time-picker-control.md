---
title: "Использование полей обратного вызова выбора даты и времени элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
dev_langs: C++
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e5526b0f8826a91eb0b1c5a6eae250abbb02fcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Использование полей обратного вызова элемента выбора даты и времени
Кроме стандартных символов формата, определяющих поля выбора даты и времени можно настроить выходных данных, указав определенные части строки настраиваемого формата в качестве поля обратного вызова. Чтобы объявить поле обратного вызова, включите в один или несколько символов «X» (88 код ASCII) в любом месте строки формата. Например, следующая строка «"на сегодняшний день является: «yy» / «Мм» и «ДД» (день «X»)" «заставляет элемент управления выбора даты и времени для отображения текущего значения в виде года, месяца, даты и наконец день года.  
  
> [!NOTE]
>  Количество крестиками в обратном вызове поля не соответствует число символов, которые будут отображаться.  
  
 Может различать несколько полей обратного вызова в пользовательской строки, повторив символ «X». Таким образом, строка формата «XXddddMMMdd "," yyyXXX» содержит два поля уникальный обратного вызова, «XX» и «XXX».  
  
> [!NOTE]
>  Поля обратного вызова рассматриваются как действительные поля, поэтому приложение должно быть готово для обработки **DTN_WMKEYDOWN** сообщений уведомления.  
  
 Реализация поля обратного вызова в элементе управления выбора даты и времени состоит из трех частей:  
  
-   Инициализация строкой пользовательского формата  
  
-   Обработка **DTN_FORMATQUERY** уведомления  
  
-   Обработка **DTN_FORMAT** уведомления  
  
## <a name="initializing-the-custom-format-string"></a>Инициализация строкой пользовательского формата  
 Инициализировать пользовательские строки с помощью вызова `CDateTimeCtrl::SetFormat`. Дополнительные сведения см. в разделе [с помощью строки настраиваемого формата даты и времени выбора](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md). Единый механизм для настройки строки пользовательского формата является в `OnInitDialog` функция содержащего класса диалогового окна или `OnInitialUpdate` функция содержащего класса представления.  
  
## <a name="handling-the-dtnformatquery-notification"></a>Обработка DTN_FORMATQUERY-уведомление  
 Если элемент управления выполняет синтаксический анализ строки формата, встречается поле обратного вызова, приложение отправляет **DTN_FORMAT** и **DTN_FORMATQUERY** сообщений уведомления. Строка поля обратного вызова входит в состав уведомления, можно определить, какое поле обратного вызова выполняется запрос.  
  
 **DTN_FORMATQUERY** уведомление отправляется для получения максимально допустимый размер в пикселях строки, который будет отображаться в текущее поле обратного вызова.  
  
 Чтобы правильно вычисления этого значения необходимо вычислить высоту и ширину строки, которые будут заменены в поле, в шрифтом отображения элемента управления. Реальное вычисление строки легко достигается с помощью вызова [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938) функции Win32. После определения размера, передайте значение возвращается приложению и выйдите из функцию-обработчик.  
  
 Ниже приведен один способ указания размера строки обратного вызова:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]  
  
 После вычисления размера поля текущего обратного вызова необходимо указать значение для поля. Это можно сделать в обработчике для **DTN_FORMAT** уведомления.  
  
## <a name="handling-the-dtnformat-notification"></a>Обработка DTN_FORMAT-уведомление  
 **DTN_FORMAT** уведомление будет использоваться приложением для запроса символьной строки, который будет заменен. В следующем примере показано одно из возможных способов:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]  
  
> [!NOTE]
>  Указатель на **NMDATETIMEFORMAT** найти структуру путем приведения обработчика уведомлений в правильный тип первого параметра.  
  
## <a name="see-also"></a>См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

