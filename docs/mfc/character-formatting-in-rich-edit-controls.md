---
title: "Форматирование знаков с использованием элементов управления &quot;Rich Edit&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl - класс, форматирование знаков в"
  - "форматирование [C++], знаки"
  - "элементы управления Rich Edit, форматирование знаков в"
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Форматирование знаков с использованием элементов управления &quot;Rich Edit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно использовать функции\-члены управления расширенного редактирования \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) со знаками формата и извлекать сведения о форматировании.  Для символов можно указать шрифт, размер, цвета и эффекты, как полужирный, курсив и защитить.  
  
 Можно применить форматирование символов с помощью функций\-членов [SetSelectionCharFormat](../Topic/CRichEditCtrl::SetSelectionCharFormat.md) и [SetWordCharFormat](../Topic/CRichEditCtrl::SetWordCharFormat.md).  Для определения текущего форматирования символов для выбранного текста используйте функции\-члена [GetSelectionCharFormat](../Topic/CRichEditCtrl::GetSelectionCharFormat.md).  Структура [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) используется с этими функции\-членами для определения атрибутов символов.  Одним из важных членов **CHARFORMATdwMask**.  В `SetSelectionCharFormat` и `SetWordCharFormat`, **dwMask** определяет, какие атрибуты символов будут установлены этим вызовом функции.  отчеты `GetSelectionCharFormat` атрибуты первого символа в выделении; **dwMask** определяет атрибуты, которые согласуются на протяжении выделения.  
  
 Можно также получить и задать форматирование символов «по умолчанию», которые форматирование применяется ко всем далее введенным символам.  Например, если приложение задает форматирования символов по умолчанию к типам пользователя начертание и затем знак, то этот символ полужирным шрифтом.  Для получения и форматирование по умолчанию набора символов использует функций\-членов [GetDefaultCharFormat](../Topic/CRichEditCtrl::GetDefaultCharFormat.md) и [SetDefaultCharFormat](../Topic/CRichEditCtrl::SetDefaultCharFormat.md).  
  
 » Атрибут «защищенный символов не изменяет внешний вид текста.  Если пользователь пытается изменить защищенный текст, управление расширенного редактирования отправляет его родительское окно сообщения уведомления **EN\_PROTECTED**, что родительское окно, чтобы разрешить или запретить изменение.  Чтобы открыть это сообщение уведомления, необходимо включить его с помощью функции\-члена [SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md).  Дополнительные сведения о маска события см. в разделе [Уведомления от управления расширенного редактирования](../mfc/notifications-from-a-rich-edit-control.md) далее в этом разделе.  
  
 Цвет переднего плана атрибут символов, однако цвет фона свойства элемента управления расширенного редактирования.  Для задания цвета фона используйте функции\-члена [SetBackgroundColor](../Topic/CRichEditCtrl::SetBackgroundColor.md).  
  
## См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)