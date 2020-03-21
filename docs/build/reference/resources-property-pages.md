---
title: Ресурсы
ms.date: 08/28/2019
ms.topic: article
ms.assetid: dade2f6b-c51f-4c33-9023-41956ae4b5f6
f1_keywords:
- VC.Project.VCResourceCompilerTool.PreprocessorDefinitions
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- VC.Project.VCResourceCompilerTool.Culture
- VC.Project.VCResourceCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCResourceCompilerTool.IgnoreStandardIncludePath
- VC.Project.VCResourceCompilerTool.ShowProgress
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.ResourceOutputFileName
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: 4f3688da4feb11f673e11372e5df086dc8c7e21a
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078291"
---
# <a name="resources-property-page"></a>Страница свойств ресурсов

Для настольных программ Windows сборка вызывает [компилятор ресурсов (RC. exe)](/windows/win32/menurc/resource-compiler) для добавления изображений, строковых таблиц и *RES* -файлов в двоичный файл. Свойства, представленные на этой странице свойств, передаются компилятору ресурсов, а C++ не компилятору или компоновщику. Дополнительные сведения о свойствах, перечисленных здесь, и о том, как они сопоставляются с параметрами командной строки RC, см. в разделе Использование версии- [кандидата (Командная строка RC)](/windows/win32/menurc/using-rc-the-rc-command-line-). Сведения о том, как получить доступ к страницам свойств **ресурсов** , см. [в разделе Задание C++ свойств компилятора и сборки в Visual Studio](../working-with-project-properties.md). Для программного доступа к этим свойствам см. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>.

Свойства ресурсов .NET в C++приложениях-/CLI представлены на [странице свойств управляемые ресурсы](managed-resources-property-page.md).

## <a name="preprocessor-definitions"></a>Определения препроцессора

Указывает одно или несколько определений для компилятора ресурсов. (/d [макрос])

## <a name="undefine-preprocessor-definitions"></a>Отменить определения препроцессора

Отменить определение символа. /u

## <a name="culture"></a>Язык и региональные параметры

Список языка и региональных параметров (например, английского (США) или итальянского), используемых в ресурсах. (/l [число])

## <a name="additional-include-directories"></a>Дополнительные каталоги включаемых файлов

Указывает один или несколько каталогов для добавления к пути включения; Используйте точку с запятой в качестве разделителя, если он больше одного. (/I [путь])

## <a name="ignore-standard-include-paths"></a>Игнорировать стандартные пути включаемых файлов

Не дает компилятору ресурсов искать включаемые файлы в каталогах, указанных в переменных среды INCLUDE. /X

## <a name="show-progress"></a>Отображать ход выполнения

Отправка сообщений о ходе выполнения в окно вывода. /v

## <a name="suppress-startup-banner"></a>Отключить загрузочный баннер

Отключение отображения загрузочного баннера и информационного сообщения (/NOLOGO)

## <a name="resource-file-name"></a>Имя файла ресурсов

Указывает имя файла ресурсов (/FO [файл])

## <a name="null-terminate-strings"></a>Строки завершения со значением NULL

Добавьте значения NULL ко всем строкам в таблицах строк. параметра

## <a name="see-also"></a>См. также:

[C++Справочник по страницам свойств проекта](property-pages-visual-cpp.md)