---
title: /FORCE (Назначенный файл вывода)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: af7962a4b3b5805e7e0c4d59752254c8ade17f7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292475"
---
# <a name="force-force-file-output"></a>/FORCE (Назначенный файл вывода)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Примечания

Параметр/Force предписывает компоновщику создание .exe-файл или DLL, даже если на символ существует ссылка, но не определен или определен многократно.

Параметр/Force может занять необязательный аргумент:

- Используйте/FORCE: Multiple, чтобы создать выходной файл, или не найдет параметр LINK несколько определений символа.

- Использовать параметр/FORCE: UNRESOLVED, чтобы создать выходной файл, или не найдет параметр LINK неопределенный символ. / FORCE: НЕРАЗРЕШЕННЫЕ учитывается, если символ точки записи НЕРАЗРЕШЕН.

/ FORCE без аргументов выражает как многократные и неразрешенные ссылки.

Файл, созданный с помощью этого параметра не может выполняться правильно. Компоновщик не будет инкрементная компоновка при указании параметра/FORCE.

При компиляции модуля **/CLR**, **/FORCE** не создает образ.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
