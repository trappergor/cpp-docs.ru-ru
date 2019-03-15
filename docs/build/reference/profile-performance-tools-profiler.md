---
title: /PROFILE (профилировщик средств обеспечения производительности)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: ca68ae090c6e4e6e3e10f37ac0d225faee96746a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810007"
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

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
