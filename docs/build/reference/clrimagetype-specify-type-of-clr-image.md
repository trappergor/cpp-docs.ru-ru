---
title: /CLRIMAGETYPE (указание типа образа среды CLR)
ms.date: 05/16/2019
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
ms.openlocfilehash: ee2e2ce359a4b877551adf9af71e0187b42cfd42
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837486"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (указание типа образа среды CLR)

Установите тип образа CLR в компонуемом образе.

## <a name="syntax"></a>Синтаксис

> **/CLRIMAGETYPE:** {**IJW**|**PURE**|**SAFE**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Примечания

Компоновщик принимает объекты в машинном коде, а также объекты MSIL, скомпилированные с параметром [/clr](clr-common-language-runtime-compilation.md). Параметры компилятора **/clr:pure** и **/clr:safe** не рекомендуется использовать в Visual Studio 2015 и они не поддерживаются в Visual Studio 2017 и более поздних версий. При передаче сочетания объектов разных типов в одной сборке проверяемость итогового выходного файла по умолчанию соответствует самому низкому уровню проверяемости входных модулей. Например, при передаче образа в машинном коде и образа в смешанном режиме (скомпилированного с параметром **/clr**) итоговый образ будет образом в смешанном режиме.

При необходимости указать самый низкий уровень проверяемости можно с помощью параметра **/CLRIMAGETYPE**.

Сведения о том, как определить тип образа среды файла CLR, см. в разделе [/CLRHEADER](clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните узел **Компоновщик**.

1. Выберите страницу свойств **Дополнительно**.

1. Измените значение свойства **Тип CLR-образа**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
