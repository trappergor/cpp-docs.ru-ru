---
title: "Страница свойств шаг пользовательской сборки: Общие | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs: C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63e599a2a24716de2de3e23cb3a7c2342b036b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="custom-build-step-property-page-general"></a>Страница свойств "Общие" пользовательского шага построения
Для каждого сочетания конфигурации проекта и целевой платформы в проекте можно определить пользовательское действие, которое будет выполняться при сборке проекта.  

Linux версию этой страницы см. в разделе [Свойства шага построения пользовательского (Linux C++)](../linux/prop-pages/custom-build-step-linux.md).
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Командная строка**  
 Команда, которая будет выполняться этим пользовательским действием сборки.  
  
 **Описание**  
 Сообщение, которое отображается при выполнении пользовательского действия сборки.  
  
 **Выходные данные**  
 Выходной файл, создаваемый пользовательским действием сборки. Этот параметр является обязательным для правильной работы добавочных сборок.  
  
 **Дополнительные зависимости**  
 Разделенный точками с запятой список каких-либо дополнительных входных файлов для пользовательского действия сборки.  
  
 **Выполнить после и выполнить до**  
 Эти параметры определяют, когда пользовательское действие сборки выполняется в процессе сборки относительно перечисленных целевых объектов. Наиболее часто в число целевых объектов входят BuildGenerateSources, BuildCompile и BuildLink, поскольку они представляют основные этапы процесса сборки. Другие часто используемые целевые объекты: Midl, CLCompile и Link.  
  
 Обрабатывать выходные данные как содержимое  
 Этот параметр имеет значение только для приложений Магазина Windows и Windows Phone, включающих все файлы содержимого в пакет .appx.  
  
### <a name="to-specify-a-custom-build-step"></a>Задание пользовательского действия сборки  
  
1.  В строке меню выберите **Проект**, **Свойства**. Дополнительные сведения см. в разделе [работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
2.  В **страницы свойств** диалоговом окне перейдите к **свойства конфигурации**, **настраиваемый этап сборки**, **Общие** страницы.  
  
3.  Измените параметры.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../ide/property-pages-visual-cpp.md)