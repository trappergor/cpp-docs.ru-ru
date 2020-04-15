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
ms.openlocfilehash: c4a3048bfa07e9635662534b510fa57caa091f00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336079"
---
# <a name="resources-property-page"></a>Страница свойства ресурсов

Для нацдебных программ Windows сборка вызывает в двоичный файл [ресурсный компилятор (rc.exe)](/windows/win32/menurc/resource-compiler) для добавления изображений, строк и файлов *.res.* Свойства, выставленные на этой странице свойств, передаются компилятору ресурсов, а не компилятору c's или связующим. Для получения дополнительной информации о свойствах, перечисленных здесь, и о том, как они отображают параметры командной строки RC, [см.](/windows/win32/menurc/using-rc-the-rc-command-line-) Для получения информации о том, как получить доступ к страницам свойств **Ресурсов,** [см.](../working-with-project-properties.md) Для программного доступа к этим свойствам см. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>.

Свойства ресурсов .NET в приложениях СЗ/CLI разоблачаются на [странице свойства управляемых ресурсов.](managed-resources-property-page.md)

## <a name="preprocessor-definitions"></a>Определения препроцессора

Определяет один или несколько определяет для компилятора ресурсов. (/д-макро)

## <a name="undefine-preprocessor-definitions"></a>Отменить определения препроцессора

Не определить символ. (/u)

## <a name="culture"></a>culture

Перечисляет культуру (например, английскую или итальянскую), используемую в ресурсах. (/л (num)

## <a name="additional-include-directories"></a>Дополнительные каталоги включаемых файлов

Укажите один или несколько каталогов для добавления в путь включения; использовать полуколонный делимитер, если более одного. (/Я-путь)

## <a name="ignore-standard-include-paths"></a>Игнорировать стандартные пути включения

Предотвращает поиск компилятора ресурсов, включая файлы в каталогах, указанных в переменных среды INCLUDE. (/X)

## <a name="show-progress"></a>Отображать ход выполнения

Отправка сообщений о ходе работы в окно вывода. (/v)

## <a name="suppress-startup-banner"></a>Отключить загрузочный баннер

Подавите отображение баннера запуска и информационного сообщения (/nologo)

## <a name="resource-file-name"></a>Имя файла ресурса

Упогоняет имя файла ресурса (/fo'file)

## <a name="null-terminate-strings"></a>Null Упразднение строк

Придатите null's ко всем строкам в таблицах строк. (/n)

## <a name="see-also"></a>См. также раздел

[Ссылка на свойство проекта «СИ»](property-pages-visual-cpp.md)
