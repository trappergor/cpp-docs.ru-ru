---
title: "Элементы управления ActiveX в MFC. Доступ к свойствам окружения | Microsoft Docs"
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
  - "MFC ActiveX - элементы управления, доступ к внешним свойствам"
  - "свойства [MFC], доступ к внешним"
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Элементы управления ActiveX в MFC. Доступ к свойствам окружения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот раздел описывает элемент управления ActiveX может принимать внешние свойства контейнера элементов управления.  
  
 Элемент управления может получать сведения о текущем контейнере через внешние свойства контейнера.  Эти свойства предоставляют визуальные характеристики, как цвет фона контейнера, текущий шрифт, используемый контейнером и рабочие характеристики, например ли контейнер в данный момент в режиме пользователя или в режиме конструктора.  Элемент управления может использовать внешние свойства настраивать его внешний вид и расширения функциональности к указанному контейнеру, в который он внедрен.  Однако элемент управления никогда не высказывать его контейнером будет поддерживать любое определенное внешнее свойство.  Фактически, некоторые контейнеры могут не поддерживать все свойства окружения вообще.  В отсутствие внешнего свойства, элемент управления должен следует принять значения по умолчанию.  
  
 Для получения внешнее свойство вызывать в [COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md).  Эта функция должна идентификатор обработки для внешнего свойства как первый параметр \(файл OLECTL.H определяет идентификаторов диспетчеризации для стандартного набора внешних свойств\).  
  
 Параметры функции `GetAmbientProperty` идентификатор обработки, другой тег, ожидается тип свойства и указатель на память, значение должно быть возвращено.  Тип данных, на которые ссылается этот указатель будет изменяться в зависимости от другого тега.  Функция возвращает значение **TRUE**, если контейнер поддерживает свойство, в противном случае возвращается значение **ЛОЖЬ**.  
  
 В следующем примере получается значение с именем внешнего UserMode» свойства «. Если свойство не поддерживается контейнером, значение по умолчанию **TRUE** происходит:  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/CPP/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 Для удобства вспомогательные функции `COleControl`, обращающиеся к многие часто используемые свойства окружения и возвращает соответствующие свойства по умолчанию, если не доступны.  Эти вспомогательные функции следующим образом:  
  
-   [COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)  
  
-   [AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)  
  
-   [AmbientFont](../Topic/COleControl::AmbientFont.md)  
  
    > [!NOTE]
    >  Вызывающий объект должен вызвать **Release\( \)** для возвращенного шрифтом.  
  
-   [AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)  
  
-   [AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)  
  
-   [AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)  
  
-   [AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)  
  
-   [AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)  
  
-   [AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)  
  
-   [AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)  
  
-   [AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)  
  
 Если значение свойства внешнего изменяет \(через определенное действие контейнера\), вызывается функцию\-член **OnAmbientPropertyChanged** элемента управления.  Переопределите этот функцию\-член для обработки такое уведомление.  Параметр **OnAmbientPropertyChanged** для обработки затрагиваемого внешнего идентификатор свойства.  Значение этого идентификатора обработки может быть **DISPID\_UNKNOWN**, что означает, что один или несколько внешние свойства были изменены, но сведения о том, какие свойства были затронуты недоступна.  
  
## См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)