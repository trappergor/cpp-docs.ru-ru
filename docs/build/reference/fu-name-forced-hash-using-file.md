---
title: '-FU (имя принудительно #using файл) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
dev_langs:
- C++
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acf4afebc7288a953a0f8785e1f18097c21d71e3
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107408"
---
# <a name="fu-name-forced-using-file"></a>/FU (именование файла с принудительно используемым атрибутом #using)

Параметр компилятора, который можно использовать в качестве альтернативы передачи имени файла для [# директива using](../../preprocessor/hash-using-directive-cpp.md) в исходном коде.

## <a name="syntax"></a>Синтаксис

> **/FU** *файла*

## <a name="arguments"></a>Аргументы

*file*<br/>
Указывает файл метаданных и ссылка в данной компиляции.

## <a name="remarks"></a>Примечания

/FU коммутатора принимает только одно имя файла. Чтобы указать несколько файлов, используйте /FU с каждой из них.

При использовании C + +/ CLI и ссылающихся на метаданных для использования [дружественных сборок](../../dotnet/friend-assemblies-cpp.md) функции нельзя использовать **/FU**. Должна ссылаться на метаданные в коде с помощью `#using`— вместе с `[as friend]` атрибута. Дружественные сборки не поддерживаются в расширения компонентов Visual C++ C + +/ CX.

Сведения о создании сборки или модуля для общеязыковой среды выполнения (CLR), см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md). Сведения о построении в C + +/ CX, см. в разделе [построение приложений и библиотек](../../cppcx/building-apps-and-libraries-c-cx.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **Дополнительно** страницу свойств.

1. Изменить **Force #using** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.

## <a name="see-also"></a>См. также

[Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)