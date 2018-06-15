---
title: Страница свойств "Общие" настраиваемого этапа сборки | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs:
- C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d88bd738711058794a525217ba2640e8d52356d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33325933"
---
# <a name="custom-build-step-property-page-general"></a>Страница свойств "Общие" пользовательского шага построения
Для каждого сочетания конфигурации проекта и целевой платформы в проекте можно определить пользовательское действие, которое будет выполняться при сборке проекта.  

Версию этой страницы для Linux см. в разделе [Свойства настраиваемого этапа сборки (Linux C++)](../linux/prop-pages/custom-build-step-linux.md).
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Командная строка**  
 Команда, которая будет выполняться этим пользовательским действием сборки.  
  
 **Описание**  
 Сообщение, которое отображается при выполнении пользовательского действия сборки.  
  
 **Вывод**  
 Выходной файл, создаваемый пользовательским действием сборки. Этот параметр является обязательным для правильной работы добавочных сборок.  
  
 **Дополнительные зависимости**  
 Разделенный точками с запятой список каких-либо дополнительных входных файлов для пользовательского действия сборки.  
  
 **Выполнить после и выполнить до**  
 Эти параметры определяют, когда пользовательское действие сборки выполняется в процессе сборки относительно перечисленных целевых объектов. Наиболее часто в число целевых объектов входят BuildGenerateSources, BuildCompile и BuildLink, поскольку они представляют основные этапы процесса сборки. Другие часто используемые целевые объекты: Midl, CLCompile и Link.  
  
 Обрабатывать выходные данные как содержимое  
 Этот параметр имеет значение только для приложений универсальной платформы Windows и Windows Phone, включающих все файлы содержимого в пакет APPX.  
  
### <a name="to-specify-a-custom-build-step"></a>Задание пользовательского действия сборки  
  
1.  В строке меню выберите **Проект**, **Свойства**. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
2.  В диалоговом окне **Страницы свойств** перейдите к странице **Свойства конфигурации**, **Настраиваемый этап сборки**, **Общие**.  
  
3.  Измените параметры.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../ide/property-pages-visual-cpp.md)