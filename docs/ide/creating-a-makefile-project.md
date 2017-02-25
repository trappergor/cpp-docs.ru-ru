---
title: "Создание проекта Makefile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.makefile.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Проекты, использующие файл makefile, создание"
  - "файлы проекта [C++], Проекты, использующие файл makefile"
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Создание проекта Makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если имеется проект, построенный из командной строки с использованием файла makefile, среда разработки Visual Studio не распознает этот проект.  Для открытия и сборки проекта с помощью [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], [!INCLUDE[vsPro](../ide/includes/vspro_md.md)] или Visual Studio Express для Windows Desktop сначала создайте пустой проект, выбрав шаблон проекта MakeFile.  Затем этот проект можно использовать для построения нового проекта из среды разработки Visual Studio.  
  
 Проект не отображает в обозревателе решений никаких файлов.  Проект задает параметры построения, которые показаны на странице свойства проекта.  
  
 Выходной файл, который задается в проекте, не влияет на имя, которое формирует скрипт построения; он указывает только на намерения.  
  
### Создание проекта Makefile  
  
1.  Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C\+\+](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Чтобы открыть мастер, в диалоговом окне **Новый проект** выберите **Проект Makefile** в панели "Шаблоны".  
  
3.  На странице [Параметры приложения](../ide/application-settings-makefile-project-wizard.md) предоставьте сведения о команде, выходе, удалении и повторном создании.  
  
4.  Нажмите кнопку **Готово**, чтобы закрыть мастер и открыть в **обозревателе решений** вновь созданный проект.  
  
 На этой странице свойств можно просматривать и изменять свойства проекта.  Сведения об отображении страницы свойств см. в разделе [Установка свойств проекта C\+\+](../ide/working-with-project-properties.md).  
  
## См. также  
 [мастер проекта Makefile](../ide/makefile-project-wizard.md)   
 [Специальные символы в файле makefile](../build/special-characters-in-a-makefile.md)   
 [Содержимое файла makefile](../build/contents-of-a-makefile.md)