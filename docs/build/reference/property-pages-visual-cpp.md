---
title: Справочник C++ по страницам свойств проекта Windows — Visual Studio
ms.date: 08/28/2019
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
ms.openlocfilehash: c9fd4fc00e86e0660972fc0bd37b66b2fea02ee0
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177460"
---
# <a name="windows-c-project-property-page-reference"></a>Справочник C++ по страницам свойств проекта Windows

В Visual Studio вы указываете параметры компилятора и компоновщика, пути к файлам и другие параметры сборки на страницах свойств проекта. Доступные свойства и страницы свойств зависят от типа проекта. Например, проект Makefile содержит страницу свойств NMake, которая отсутствует в проекте консоли MFC или Win32. Чтобы открыть **страницы свойств**, в главном меню выберите**Свойства** **проекта** > или щелкните правой кнопкой мыши узел проекта в **Обозреватель решений** и выберите пункт **Свойства**. Отдельные файлы также имеют страницы свойств, позволяющие задавать параметры компиляции и сборки только для этого файла. На следующем рисунке показаны страницы свойств для проекта MFC.

![Страницы свойств для C++ проекта](media/example-prop-page.png)

Этот раздел содержит краткий справочник по самим страницам свойств. Параметры и параметры, представленные на страницах свойств, задокументированы более полностью в собственных разделах и связаны с разделами страницы свойств. Дополнительные сведения о свойствах проекта см. [в C++ разделе Установка компилятора и свойств сборки в Visual Studio](../working-with-project-properties.md).

Сведения о страницах свойств в проектах Linux см. в разделе [Справочник по страницам свойств Linux C++ ](../../linux/prop-pages-linux.md).

## <a name="in-this-section"></a>В этом разделе

- [Страница свойств "Общие" (проект)](general-property-page-project.md)
- [Страница свойств "Общие" (файл)](general-property-page-file.md)
- [Страница свойств «Дополнительно»](advanced-property-page.md)
- [Страница свойств каталогов VC++](vcpp-directories-property-page.md)
- [Страницы свойств компоновщика](linker-property-pages.md)
- [Страницы свойств инструмента манифеста](manifest-tool-property-pages.md)
- [Страницы свойств HLSL](hlsl-property-pages.md)
- [Страницы свойств командной строки](command-line-property-pages.md)
- [Страница свойств настраиваемого этапа сборки: общие](custom-build-step-property-page-general.md)
- [Добавление ссылок](../adding-references-in-visual-cpp-projects.md)
- [Страница свойств управляемых ресурсов](managed-resources-property-page.md)
- [Страницы свойств MIDL](midl-property-pages.md)
- [Страница свойств NMake](nmake-property-page.md)
- [Страницы свойств ресурсов](resources-property-pages.md)
- [Страница свойств веб-ссылок](web-references-property-page.md)
- [Страница свойств "Инструмент создания XML-данных"](xml-data-generator-tool-property-page.md)
- [Страницы свойств средства создания XML-документов](xml-document-generator-tool-property-pages.md)

## <a name="see-also"></a>См. также

[Практическое руководство. Создание и удаление зависимостей проекта](/visualstudio/ide/how-to-create-and-remove-project-dependencies)<br/>
[Практическое руководство. Создание и изменение конфигураций](/visualstudio/ide/how-to-create-and-edit-configurations)<br/>
[Справочник C++ по страницам свойств Linux](../../linux/prop-pages-linux.md)
