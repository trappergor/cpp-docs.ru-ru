---
title: "мастер DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.dll.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "мастер DLL [MFC]"
  - "DLL-библиотеки [C++], создание"
  - "DLL-библиотеки [C++], MFC - библиотека"
  - "мастер DLL [MFC]"
  - "библиотеки DLL MFC [C++]"
  - "библиотеки DLL MFC [C++], создание"
ms.assetid: 4e936031-7e39-4f40-a295-42a09c5ff264
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# мастер DLL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При использовании мастера MFC DLL для создания проекта MFC DLL, разработчик получает работающее приложение со встроенной функциональностью, которая после компиляции будет реализовывать основные возможности [DLL](../../build/dlls-in-visual-cpp.md).  Начальная программа MFC включает файлы исходного кода C\+\+ \(CPP\-файлы\), файлы ресурсов \(RC\-файлы\) и файл проекта \(VCXPROJ\-файл\).  Код, созданный в этих начальных файлах, основан на MFC.  Дополнительные сведения см. в разделе "Сведения о файле" файла Readme.txt, который создается для проекта в Visual Studio и в [Классы и функции, создаваемые мастером MFC DLL](../Topic/Classes%20and%20Functions%20Generated%20by%20the%20MFC%20DLL%20Wizard.md).  
  
## Обзор  
 На этой странице мастера описываются [текущие параметры приложения для создаваемого проекта MFC DLL](../../mfc/reference/application-settings-mfc-dll-wizard.md).  По умолчанию проект создается как обычный проект DLL \(MFC Shared\) без дополнительных параметров.  
  
 Чтобы изменить параметры, заданные по умолчанию, в левой колонке мастера выберите вкладку **Параметры приложения** и внесите необходимые изменения на странице мастера проектов MFC DLL.  
  
 После создания проекта MFC DLL в него можно добавить объекты и элементы управления, используя [мастера кода](../../ide/adding-functionality-with-code-wizards-cpp.md) Visual C\+\+.  
  
 Для основного проекта MFC DLL можно выполнить следующие задачи и виды расширения:  
  
-   [Экспорт из DLL](../../build/exporting-from-a-dll.md)  
  
-   [Связывание исполняемого файла с DLL](../../build/linking-an-executable-to-a-dll.md)  
  
-   [Инициализацию DLL](../../build/initializing-a-dll.md)  
  
## См. также  
 [Создание проектов Visual C\+\+ и управление ими](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Работа со свойствами проектов](../../ide/working-with-project-properties.md)   
 [Deploying Applications](http://msdn.microsoft.com/ru-ru/4ff8881d-0daf-47e7-bfe7-774c625031b4)   
 [Класс MFC](../../mfc/reference/adding-an-mfc-class.md)   
 [Добавление функции\-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Реализация интерфейса](../../ide/implementing-an-interface-visual-cpp.md)   
 [Поддержка мастера для других языков](../../ide/wizard-support-for-other-languages.md)