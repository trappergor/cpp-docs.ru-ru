---
title: /CLRIMAGETYPE (указание типа образа среды CLR)
ms.date: 11/04/2016
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
ms.openlocfilehash: c4cdb9a9ac3376762d6aa40fd4c13abbdc7b5487
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461637"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (указание типа образа среды CLR)

Задайте тип образа среды CLR в связанное изображение.

## <a name="syntax"></a>Синтаксис

> **/ CLRIMAGETYPE:**{**IJW**|**ЧИСТЫЙ**|**БЕЗОПАСНОМ**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Примечания

Компоновщик принимает собственных объектов, а также MSIL объекты, скомпилированные с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). **/CLR: pure** и **/CLR: safe** параметры компилятора стали нерекомендуемыми в Visual Studio 2015 и не поддерживаются в Visual Studio 2017. При передаче смешанных объектов в той же сборки, является проверяемость выходного файла по умолчанию, равное минимальному уровню проверяемости входных модулей. Например, если передать образ в машинном коде и смешанного режима (скомпилированные с помощью **/CLR**), полученное изображение будет смешанного режима.

Можно использовать **/CLRIMAGETYPE** для указания более низкий уровень проверяемости, если это то, что вам нужно.

Сведения о том, как определить тип образа среды файла CLR, см. в разделе [/CLRHEADER](../../build/reference/clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **Дополнительно** страницу свойств.

1. Изменить **тип образа среды CLR** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)
