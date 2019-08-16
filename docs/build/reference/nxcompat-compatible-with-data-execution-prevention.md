---
title: /NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: 7c788f5ec499f0edf0c44f1ff269af9767af6c08
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492665"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))

Указывает, что исполняемый файл совместим с функцией предотвращения выполнения данных Windows.

## <a name="syntax"></a>Синтаксис

> **/NXCOMPAT** [ **: НЕТ**]

## <a name="remarks"></a>Примечания

По умолчанию **/NXCOMPAT** имеет значение ON.

**/NXCOMPAT: No** можно использовать для явного указания исполняемого файла в качестве несовместимого с предотвращением выполнения данных.

Дополнительные сведения об предотвращении выполнения данных см. в следующих статьях:

- [Подробное описание функции предотвращения выполнения данных (DEP)](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [Предотвращение выполнения данных](/windows/win32/Memory/data-execution-prevention)

- [Предотвращение выполнения данных (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойства**командной строки** **компоновщика** >  **свойств** > конфигурации.

1. Введите параметр в поле **Дополнительные параметры** . Нажмите кнопку **ОК** или **Применить** , чтобы применить изменение.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
