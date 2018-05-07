---
title: Создание проекта Makefile | Документы Microsoft
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc854f96f1c41baf28a5af4ca1f253e47d9a8914
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-makefile-project"></a>Создание проекта Makefile

Если имеется существующий проект исходного кода при построении из командной строки с использованием файла makefile, среда разработки Visual Studio имеет несколько способов преобразования его в проект, можно воспользоваться всеми преимуществами компоненты Visual Studio IDE. В этой статье описывается создание проекта Makefile в Visual Studio, которая использует существующего файла makefile для создания кода в Интегрированной среде разработки. Кроме того, можно использовать **Создание нового проекта из существующих файлов кода** мастера для создания собственного проекта MSBuild из исходного кода. Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта C++ из существующего кода](how-to-create-a-cpp-project-from-existing-code.md). Начиная с Visual Studio 2017 г., можно использовать **открыть папку** компонент, который можно использовать несколько существующих систем сборки, как если бы они были собственных проектов Visual Studio. Дополнительные сведения см. в статье [Open Folder projects in Visual C++](non-msbuild-projects.md) (Открытие папки проектов в Visual C++).

В Visual Studio можно использовать для открытия и сборки исходного кода с помощью существующего файла makefile, сначала создайте новый проект, выбрав шаблон проекта MakeFile. Мастер поможет вам указать команды и среды, используемого файла makefile. Затем этот проект можно использовать для создания кода в среде разработки Visual Studio.

По умолчанию проекта makefile отображает файлы в обозревателе решений. Проект makefile указывает параметры сборки, которые показаны на странице свойств проекта.

Выходной файл, который задается в проекте, не влияет на имя, которое формирует скрипт построения; он указывает только на намерения. По-прежнему файла makefile управляющий процессом сборки и указывает целевых объектов построения.

## <a name="to-create-a-makefile-project"></a>Создание проекта Makefile

1. Следуйте инструкциям в разделе справки [Создание проекта с использованием мастера приложений Visual C++](../ide/creating-desktop-projects-by-using-application-wizards.md).

1. В **новый проект** диалогового окна разверните **Visual C++** > **Общие** , а затем выберите **проекта Makefile** в Чтобы открыть мастер проекта «шаблоны».

1. В [параметры приложения](../ide/application-settings-makefile-project-wizard.md) укажите выводе команды очистки и перестроения сведения для отладки и розничной торговли построения.

1. Нажмите кнопку **Готово** закрыть мастер и открыть проект, созданный в **обозревателе решений**.

На этой странице свойств можно просматривать и изменять свойства проекта. В разделе [задание свойств проекта Visual C++](../ide/working-with-project-properties.md) сведения об отображении страницы свойств.

## <a name="see-also"></a>См. также

[Мастер проекта Makefile](../ide/makefile-project-wizard.md)<br/>
[Специальные символы в файле Makefile](../build/special-characters-in-a-makefile.md)<br/>
[Содержимое файла Makefile](../build/contents-of-a-makefile.md)<br/>
