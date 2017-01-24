---
title: "Поддерживаемые платформы (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "платформы [C++]"
  - "Visual C++, поддерживаемые платформы"
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Поддерживаемые платформы (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приложения, разработанные с помощью [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], могут быть нацелены на различные платформы, а именно:  
  
|Операционная система|x86|x64|ARM|  
|--------------------------|---------|---------|---------|  
|Windows XP|X\*|X\*||  
|[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|X\*|X\*||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android \*\*|X|X|X|  
|iOS \*\*|X|X|X|  
  
 \* Можно использовать Набор инструментов платформы Windows XP, включенный в Visual Studio 2015, Visual Studio 2013 и Visual Studio 2012 с обновлением 1 или более позднюю версию для построения проектов Windows XP и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Сведения об использовании этого набора инструментов платформы см. в разделе [Настройка программ C\+\+ 11 для Windows XP](../build/configuring-programs-for-windows-xp.md).  Дополнительную информацию об изменении набора инструментов платформы см. в разделе [Практическое руководство. Изменение требуемой версии .NET Framework и набора средств платформы](../build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
 \*\* Вы можете установить дополнительный компонент Visual C\+\+ для кроссплатформенной мобильной разработки при настройке Visual Studio 2015, чтобы выбрать целевую платформу iOS или Android.  Инсрукции см. в разделе [Установка Visual C\+\+ для разработки кроссплатформенных мобильных приложений](../Topic/Install%20Visual%20C++%20for%20Cross-Platform%20Mobile%20Development.md).  Для создания кода iOS необходимо иметь компьютер Mac и выполнить другие требованиям.  Список необходимых условий и инструкции для установки см. в разделе [Установка и настройка средств для разработки с помощью iOS](../Topic/Install%20And%20Configure%20Tools%20to%20Build%20using%20iOS.md).  Вы можете создавать код x86 или ARM для соответствия целевому оборудованию.  Используйте конфигурацию x86 для создания кода для имитатора iOS, Microsoft Visual Studio Emulator для Android и некоторых устройств Android.  Используйте конфигурацию ARM для создания кода для устройств iOS и большинства устройств Android.  
  
 Информацию о том, как задать конфигурацию целевой платформы, см. в разделе [Практическое руководство. Настройка проектов Visual C\+\+ для 64\-разрядных платформ](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
## См. также  
 [Инструменты и шаблоны Visual C\+\+ в выпусках Visual Studio](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)   
 [Начало работы](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md)