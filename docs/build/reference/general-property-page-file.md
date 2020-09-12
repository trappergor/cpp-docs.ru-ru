---
title: Страница свойств "Общие" (файл)
ms.date: 08/30/2019
f1_keywords:
- VC.Project.VCFileConfiguration.ExcludedFromBuild
- VC.Project.VCFileConfiguration.Tool
ms.assetid: 26e3711e-9e7d-4e8d-bc4c-2474538efdad
ms.openlocfilehash: 7626e161e6f59de32d426b558827c423a0bb050d
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041384"
---
# <a name="general-property-page-file"></a>Страница свойств "Общие" (файл)

Этот раздел относится к проектам Windows. Для проектов, отличных от Windows, см. раздел [Ссылка на страницу свойств C++ для Linux](../../linux/prop-pages-linux.md).

Если щелкнуть правой кнопкой мыши узел файла **Обозреватель решений**, откроется страница свойств **Общие** в узле **Свойства конфигурации** . Он содержит следующие свойства:

- **Исключено из сборки**

   Определяет, должен ли файл входить в сборку для текущей конфигурации.

   Для программного доступа к этому свойству см. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.ExcludedFromBuild%2A>.

- **Содержимое** (применяется только к приложениям UWP.) Указывает, содержит ли файл содержимое, включаемое в пакет приложения.

- **Тип элемента**

   **Тип элемента** определяет средство, которое будет использоваться для обработки файла в процессе сборки. [Файлы, расширение которых известно Visual Studio](/visualstudio/extensibility/visual-cpp-project-extensibility#project-items) , имеют значение по умолчанию в этом свойстве. Если имеется пользовательский тип файла или требуется переопределить средство по умолчанию для известного типа файлов, можно указать пользовательское средство. Дополнительные сведения см. в разделе [Задание пользовательских средств сборки](../specifying-custom-build-tools.md). Можно также использовать эту страницу свойств, чтобы указать, что файл не является частью процесса сборки.

   На следующем рисунке показана страница свойств для *cpp* -файла. **Тип элемента** по умолчанию для этого типа файлов — **компилятор C/C++** (*cl.exe*), а на странице свойств отображаются различные параметры компилятора, которые могут быть применены только к этому файлу.

   ![Страница свойств "Общие" для элемента проекта](media/file-general-item-type.png "Выбор типа элемента")

    В следующей таблице перечислены типы элементов по умолчанию.

    |Расширение файла|Тип элемента|Инструмент по умолчанию|
    |-|-|-|
    |APPX|Определение приложения XAML|[Упаковщик приложений](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |. HLSL,. cso|Компилятор HLSL|[fxc.exe](/windows/win32/direct3dtools/fxc)|
    |.h|Заголовок C/C++|[Препроцессор C/C++](../../preprocessor/c-cpp-preprocessor-reference.md)|
    |Н/Д|Не участвует в сборке|Н/Д|
    |. XML,. XSLT,. xsl|Xml|[Редактор XML](/visualstudio/xml-tools/xml-editor)|
    |. resw,. resjson|Ресурс PRI (приложения UWP)|[MakePri.exe](/windows/uwp/app-resources/compile-resources-manually-with-makepri)|
    ||Носитель (UWP)|[Упаковщик приложений](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.xsd|Инструмент создания XML-данных|[Инструмент определения схемы XML (Xsd.exe)](/dotnet/standard/serialization/xml-schema-definition-tool-xsd-exe) (требуется рабочая нагрузка .NET. Не входит в состав КОМПИЛЯТОРОМ MSVC.)|
    ||Инструмент манифеста|[mt.exe](/windows/win32/sbscs/mt-exe)|
    |.rc|Ресурс|[Компилятор ресурсов Windows (rc.exe)](/windows/win32/menurc/resource-compiler)|
    |. appxmanifest|Манифест пакета приложения|[Упаковщик приложений](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.obj|Объект|[Компоновщик C/C++ (link.exe)](cl-invokes-the-linker.md)|
    |.ttf|Шрифт|Н/Д|
    |.txt|текст|Н/Д|
    |Н/Д|Настраиваемое средство сборки|Определяемые пользователем маршруты|
    |Н/Д|Копировать файл|Н/Д|
    |. packagelayout|Макет пакета приложения|[Упаковщик приложений](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.resx|Управляемый компилятором ресурс|[Resgen.exe (генератор файлов ресурсов)](/dotnet/framework/tools/resgen-exe-resource-file-generator)|
    |. natvis|Файл визуализации отладчика C++|[Платформа Natvis](/visualstudio/debugger/create-custom-views-of-native-objects)|
    |JPG, BMP, ICO и т. д.|Образ —|Компилятор ресурсов на основе типа приложения.|
    |.cpp|Компилятор C/C++|cl.exe|

   Для программного доступа к этому свойству см. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.Tool%2A>.

Дополнительные сведения о доступе к странице свойств **Общие** в узле **Свойства конфигурации** см. в разделе [Установка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

## <a name="see-also"></a>См. также

[Справочник по страницам свойств проекта C++](property-pages-visual-cpp.md)
