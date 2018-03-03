---
title: "Создание проекта Makefile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e86bedbf83cd417cfc41317e5887304cda7ee76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-makefile-project"></a>Создание проекта Makefile
Если имеется проект, построенный из командной строки с использованием файла makefile, среда разработки Visual Studio не распознает этот проект. Чтобы открыть и строить проект с помощью [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], Visual Studio Professional или Visual Studio Express для Windows Desktop, сначала создайте пустой проект, выбрав шаблон проекта MakeFile. Затем этот проект можно использовать для построения нового проекта из среды разработки Visual Studio.  
  
 Проект не отображает в обозревателе решений никаких файлов. Проект задает параметры построения, которые показаны на странице свойства проекта.  
  
 Выходной файл, который задается в проекте, не влияет на имя, которое формирует скрипт построения; он указывает только на намерения.  
  
### <a name="to-create-a-makefile-project"></a>Создание проекта Makefile  
  
1.  Следуйте инструкциям в разделе справки [Создание проекта с использованием мастера приложений Visual C++](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  В **новый проект** выберите **проекта Makefile** в области шаблонов, чтобы открыть мастер.  
  
3.  В [параметры приложения](../ide/application-settings-makefile-project-wizard.md) введите команду, выходные данные, очистить и перестроить сведения.  
  
4.  Нажмите кнопку **Готово** закрыть мастер и открыть проект, созданный в **обозревателе решений**.  
  
 На этой странице свойств можно просматривать и изменять свойства проекта. В разделе [задание свойств проекта Visual C++](../ide/working-with-project-properties.md) сведения об отображении страницы свойств.  
  
## <a name="see-also"></a>См. также  
 [Мастер проекта makefile](../ide/makefile-project-wizard.md)   
 [Специальные символы в файле Makefile](../build/special-characters-in-a-makefile.md)   
 [Содержимое файла Makefile](../build/contents-of-a-makefile.md)