---
title: / CLRIMAGETYPE (указание типа образа среды CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs:
- C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5efb2e73e854591be7134753cec21a708fff3e5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705014"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (указание типа образа среды CLR)

Задайте тип образа среды CLR в связанное изображение.

## <a name="syntax"></a>Синтаксис

> **/ CLRIMAGETYPE:**{**IJW**|**ЧИСТЫЙ**|**БЕЗОПАСНОМ**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Примечания

Компоновщик принимает собственных объектов, а также MSIL объекты, которые были скомпилированы с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). **/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017 г. При передаче смешанных объектов в той же сборки, является проверяемости выходного файла по умолчанию, равное минимальному уровню проверяемости входных модулей. Например, если передать образ в машинном коде и образ смешанного режима (скомпилированный с помощью **/CLR**), полученное изображение будет смешанного режима.

Можно использовать **/CLRIMAGETYPE** для указания более низкий уровень проверяемости, если необходимые условия.

Сведения о том, как определить тип образа среды файла CLR, см. в разделе [/CLRHEADER](../../build/reference/clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните **свойства конфигурации** узла.

1. Разверните **компоновщика** узла.

1. Выберите **Дополнительно** страницу свойств.

1. Изменить **тип образа среды CLR** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)
