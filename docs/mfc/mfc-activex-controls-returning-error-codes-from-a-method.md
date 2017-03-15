---
title: "Элементы управления ActiveX в MFC. Возврат кодов ошибок из метода | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ошибки [C++], коды ошибок элементов управления ActiveX"
  - "FireError - метод"
  - "GetNotSupported - метод"
  - "MFC ActiveX - элементы управления, коды ошибок"
  - "SCODE, MFC ActiveX - элементы управления"
  - "SetNotSupported - метод, использование"
  - "ThrowError - метод"
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Элементы управления ActiveX в MFC. Возврат кодов ошибок из метода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье описывается, как вернуть код ошибки из метода элемента управления ActiveX.  
  
 Чтобы указать, что произошла ошибка в методе, необходимо использовать функции\-члена [COleControl::ThrowError](../Topic/COleControl::ThrowError.md), который принимает `SCODE` \(код состояния\) в качестве параметра.  Можно использовать предопределенное `SCODE` или укажите одно из.  
  
> [!NOTE]
>  если используется, чтобы `ThrowError` только для средство возврат ошибки из свойства получает или задана функция или метод автоматизации.  Это единственные времени, соответствующий обработчик исключений будет в стеке.  
  
 Вспомогательные функции существуют самого общего предопределенного `SCODE` s, например [COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md), [COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md) и [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md).  
  
 Для списка предопределило `SCODE` и инструкции, определения пользовательского `SCODE` s, см. в разделе [Обработка ошибок в коде элемента управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX. Дополнительные разделы.  
  
 Дополнительные сведения об исключениях отчета в других областях кода см. в разделе [COleControl::FireError](../Topic/COleControl::FireError.md) и [Обработка ошибок в коде элемента управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX. Дополнительные разделы.  
  
## См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)