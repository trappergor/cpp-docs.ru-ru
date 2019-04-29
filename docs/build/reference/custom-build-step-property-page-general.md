---
title: 'Страница свойств настраиваемого этапа сборки: Общие'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
ms.openlocfilehash: 329923140cf5a8f05e5c032ddb9e25c0ea45ec2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273083"
---
# <a name="custom-build-step-property-page-general"></a>Страница свойств настраиваемого этапа сборки: Общие

Для каждого сочетания конфигурации проекта и целевой платформы в проекте можно определить пользовательское действие, которое будет выполняться при сборке проекта.

Версию этой страницы для Linux см. в разделе [Свойства настраиваемого этапа сборки (Linux C++)](../../linux/prop-pages/custom-build-step-linux.md).

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Командная строка**

   Команда, которая будет выполняться этим пользовательским действием сборки.

- **Описание**

   Сообщение, которое отображается при выполнении пользовательского действия сборки.

- **Вывод**

   Выходной файл, создаваемый пользовательским действием сборки. Этот параметр является обязательным для правильной работы добавочных сборок.

- **Дополнительные зависимости**

   Разделенный точками с запятой список каких-либо дополнительных входных файлов для пользовательского действия сборки.

- **Выполнить после и выполнить до**

   Эти параметры определяют, когда пользовательское действие сборки выполняется в процессе сборки относительно перечисленных целевых объектов. Наиболее часто в число целевых объектов входят BuildGenerateSources, BuildCompile и BuildLink, поскольку они представляют основные этапы процесса сборки. Другие часто используемые целевые объекты: Midl, CLCompile и Link.

- **Обрабатывать выходные данные как содержимое**

   Этот параметр имеет значение только для приложений универсальной платформы Windows и Windows Phone, включающих все файлы содержимого в пакет APPX.

### <a name="to-specify-a-custom-build-step"></a>Задание пользовательского действия сборки

1. В строке меню выберите **Проект**, **Свойства**. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. В диалоговом окне **Страницы свойств** перейдите к странице **Свойства конфигурации**, **Настраиваемый этап сборки**, **Общие**.

1. Измените параметры.

## <a name="see-also"></a>См. также

[Справочник по страницам свойств проекта C++](property-pages-visual-cpp.md)
