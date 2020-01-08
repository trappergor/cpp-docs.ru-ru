---
title: /NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))
description: Описывает параметр компоновщика MicrosoftC++ C/(компилятором MSVC)/NXCOMPAT, который помечает исполняемый файл как совместимый с предотвращением выполнения данных (DEP).
ms.date: 12/17/2019
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: f3a0906a49e3524fff3e1ef1643d1eceee28f169
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298991"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))

Указывает, что исполняемый файл совместим с функцией предотвращения выполнения данных Windows.

## <a name="syntax"></a>Синтаксис

> **/NXCOMPAT**[ **: нет**]

## <a name="remarks"></a>Заметки

По умолчанию **/NXCOMPAT** имеет значение ON.

**/NXCOMPAT: No** можно использовать для явного указания исполняемого файла в качестве несовместимого с предотвращением выполнения данных.

Дополнительные сведения об предотвращении выполнения данных см. в следующих статьях:

- [Предотвращение выполнения данных](/windows/win32/Memory/data-execution-prevention)

- [Предотвращение выполнения данных (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Свойства конфигурации** > **Компоновщик** > страницу свойств **Командная строка** .

1. Введите параметр в поле **Дополнительные параметры** . Нажмите кнопку **ОК** или **Применить** , чтобы применить изменение.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также:

\ [ссылки компоновщика компилятором MSVC](linking.md)
[Параметры компоновщика MSVC](linker-options.md)
