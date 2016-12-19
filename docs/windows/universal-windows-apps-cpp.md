---
title: "Универсальные приложения Windows (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Универсальные приложения Windows (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приложения универсальной платформы Windows \(UWP\) реализуют набор принципов разработки, выделяющих простые пользовательские интерфейсы, организованные вокруг содержимого, которое автоматически настраивается в соответствии с разными размерами экранов на разных устройствах. Для создания пользовательского интерфейса используется разметка XAML, а для кода — неуправляемый код C\+\+. Можно также создавать компоненты \(DLL\), которые могут применяться приложениями UWP, написанными на других языках. Область API для приложений UWP представляет собой [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] — хорошо организованную библиотеку, которая предоставляет широкий набор служб для операционной системы.  
  
> [!NOTE]
>  Большая часть документации для разработки приложений UWP на C\+\+ находится на веб\-сайте [Центра разработчиков Windows](http://go.microsoft.com/fwlink/p/?LinkId=255563). Некоторые приведенные в этой статье ссылки ведут на данный веб\-сайт.  
  
## Приложения UWP, использующие C\+\+\/CX  
  
|||  
|-|-|  
|[Справочник по языку Visual C\+\+ \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=255561)|Описание набора расширений, которые упрощают использование интерфейсов API [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] C\+\+ и обеспечивают обработку ошибок, основанную на исключениях.|  
|[Построение приложений и библиотек \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=264858)|Описание создания библиотек DLL и статических библиотек, доступных из приложения или компонента C\+\+\/CX.|  
|[Учебник. Создание первого приложения для Магазина Windows на C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255556)|Пошаговое руководство, представляющее основные понятия разработки приложений [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] на C\+\+. \(Еще не обновлено для разработки UWP на платформе Windows 10\).|  
|[Схема создания приложений на С\+\+ для Магазина Windows](http://go.microsoft.com/fwlink/p/?LinkId=255553)|Ссылки на статьи о разработке приложений [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] и игр на C\+\+.|  
|[Создание компонентов среды выполнения Windows в C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255559)|Описание создания библиотек DLL, которые могут использовать приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] и компоненты.|  
|[Разработка игр](http://go.microsoft.com/fwlink/p/?LinkId=255554)|Описание использования DirectX и C\+\+ для создания игр.|  
  
## Приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], использующие [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] предоставляет низкоуровневые интерфейсы COM, с помощью которых код C\+\+ ISO может обращаться к [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] в среде без поддержки исключений. В большинстве случаев вместо [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] рекомендуется использовать C\+\+\/CX для разработки приложений [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]. Дополнительные сведения о [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] см. в разделе [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md).  
  
## См. также  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)