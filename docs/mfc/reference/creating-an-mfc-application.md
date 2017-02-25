---
title: "Создание приложения MFC | Microsoft Docs"
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
  - "приложения [MFC]"
  - "MFC [C++], создание приложений"
  - "приложения MFC"
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Создание приложения MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Приложение MFC является исполняемым приложением для Windows на основе библиотеки Microsoft Foundation Class \(MFC\).  Наиболее простым способом создания приложения MFC является использование мастера приложений MFC.  
  
> [!IMPORTANT]
>  Проекты MFC не поддерживаются в выпусках Visual Studio Express.  
  
 Исполняемые приложения MFC в целом делятся на пять типов: стандартные приложения Windows, диалоговые окна, приложения на основе форм, приложения в стиле проводника и приложения в стиле браузера.  Дополнительные сведения см. в следующих разделах:  
  
-   [Использование классов для создания приложений Windows](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md)  
  
-   [Создание и отображение диалоговых окон](../../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Создание приложений MFC на основе форм](../Topic/Creating%20a%20Forms-Based%20MFC%20Application.md)  
  
-   [Создание приложения MFC в стиле проводника](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)  
  
-   [Создание приложения MFC в стиле браузера](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)  
  
 Мастер приложений MFC создает соответствующие классы и файлы для приложений любого типа в зависимости от параметров, выбранных в мастере.  
  
### Создание приложения MFC при помощи мастера приложений MFC.  
  
1.  Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C\+\+](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Чтобы открыть мастер, в диалоговом окне **Создание проекта** выберите в области "Шаблоны" элемент **Приложение MFC**.  
  
3.  Задайте параметры приложения при помощи [Мастера приложений MFC](../Topic/MFC%20Application%20Wizard.md).  
  
    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.  
  
4.  Нажмите кнопку **Готово** для завершения работы мастера и откройте новый проект в среде разработки.  
  
 После создания проекта можно просмотреть его файлы при помощи **обозревателя решений**.  Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt.  Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## См. также  
 [Debugging Preparation: Visual C\+\+ Windows Applications](http://msdn.microsoft.com/ru-ru/a8bc54de-41a3-464d-9a12-db9bdcbc1ad5)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ru-ru/4ff8881d-0daf-47e7-bfe7-774c625031b4)