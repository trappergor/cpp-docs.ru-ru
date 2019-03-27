---
title: /bigobj (Увеличение количества разделов в OBJ-файле)
ms.date: 03/26/2019
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: 46399dc0c1ff552b4fc963b686ac6aa6df8b6f71
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508719"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Увеличение количества разделов в OBJ-файле)

**/ bigobj** увеличивает число разделов, которые могут содержать объектный файл.

## <a name="syntax"></a>Синтаксис

> **/bigobj**

## <a name="remarks"></a>Примечания

По умолчанию объектный файл может содержать до 65279 (почти 2 ^ 16) адресуемых секций. Это ограничение применяется независимо от того, какой целевой платформы указан. **/ bigobj** увеличивает его адрес емкость до 4 294 967 296 (2 ^ 32).

Большинство модулей никогда не создаются OBJ-файл, содержащий более чем 65,279 разделы. Тем не менее автоматически сгенерированный код или код, усложняет использование библиотеки шаблонов может потребоваться OBJ-файлы, которые могут содержать дополнительные разделы. **/ bigobj** включена по умолчанию в проектах универсальной платформы Windows (UWP), так как автоматически сгенерированный код XAML содержит большое количество заголовков. Если вы отключаете этот параметр на проект приложения UWP, ваш код может создавать ошибку компилятора C1128.

Сведения о формате файла объект PE COFF см. в разделе [формата PE](/windows/desktop/debug/pe-format) в документации по Windows.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Введите **/bigobj** параметр компилятора в **Дополнительные параметры** поле.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
