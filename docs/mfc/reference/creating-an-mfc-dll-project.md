---
title: "Создание проекта библиотеки DLL MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcdll.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL-библиотеки [C++], создание"
  - "DLL-библиотеки [C++], MFC - библиотека"
  - "библиотеки DLL MFC [C++], создание проектов"
  - "проекты [C++], создание"
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Создание проекта библиотеки DLL MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Библиотека DLL MFC — это двоичный файл, служащий в качестве совместно используемой библиотеки функций, которая может одновременно использоваться несколькими приложениями.  Самый простой способ создания проекта библиотеки DLL MFC — использование мастера DLL MFC.  
  
> [!NOTE]
>  Вид функций в интегрированной среде разработки может зависеть от текущих настроек или выпуска и отличаться от описанного в справке.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Создание проекта библиотеки DLL MFC с помощью мастера DLL MFC  
  
1.  Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C\+\+](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Примечание** В диалоговом окне **Новый проект** выберите значок `MFC DLL` на панели "Шаблоны", чтобы открыть мастер библиотек DLL MFC.  
  
1.  Задайте параметры приложения с помощью страницы [Параметры приложения](../../mfc/reference/application-settings-mfc-dll-wizard.md) в [Мастере DLL MFC](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.  
  
2.  Нажмите кнопку **Готово**, чтобы закрыть мастер и открыть новый проект в окне **Обозреватель решений**.  
  
 После создания проекта созданные файлы можно просмотреть при помощи обозревателя решений.  Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt.  Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## См. также  
 [Типы проектов Visual C\+\+](../Topic/Debugging%20Preparation:%20Visual%20C++%20Project%20Types.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ru-ru/4ff8881d-0daf-47e7-bfe7-774c625031b4)