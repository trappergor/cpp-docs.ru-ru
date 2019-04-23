---
title: /PROFILE (профилировщик средств обеспечения производительности)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 23cbccba9a8ec839252d553cc5cbafd37e66bbf9
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124776"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (профилировщик средств обеспечения производительности)

Создает выходной файл, который может быть использован для профилировщика производительности инструментов.

## <a name="syntax"></a>Синтаксис

```
/PROFILE
```

## <a name="remarks"></a>Примечания

/ PROFILE подразумевает следующие параметры компоновщика:

- [/ OPT: REF](opt-optimizations.md)

- /OPT:NOICF

- [/ INCREMENTAL: NO](incremental-link-incrementally.md)

- [/ FIXED: NO](fixed-fixed-base-address.md)

/ PROFILE предписывает компоновщику создавать секцию перемещения в образе программы.  Он позволяет профилировщику преобразовать образ программы, чтобы получить данные профилирования.

**/ ПРОФИЛИРОВАНИЕ** доступна только в версиях Enterprise (коллективной разработке).  Дополнительные сведения о PREfast см. в разделе [анализ кода для C/C++ Обзор](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **Дополнительно** страницу свойств.

1. Изменить **профиль** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>Установка данного параметра компоновщика в пределах проекта Visual Studio CMake

**CMake** проект не содержит **страницы свойств**, параметры компоновщика можно установить с modifing CMakeLists.txt.

1. Откройте CMakeLists.txt в корневом каталоге проекта.

1. Добавьте приведенный ниже код. Дополнительные сведения см. в разделе [ссылки CMake](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)

1. Постройте решение заново.

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)

