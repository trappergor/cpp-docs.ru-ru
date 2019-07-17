---
title: /FORCE (Назначенный файл вывода)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: 28b1c21382832c8775ffe0406038a482e74076c5
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299724"
---
# <a name="force-force-file-output"></a>/FORCE (Назначенный файл вывода)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Примечания

Параметр/FORCE указывает компоновщику создать допустимый exe-файл или библиотеку DLL, даже если на символ имеется ссылка, но он не определен или определен несколько раз.

Параметр/FORCE может принимать необязательный аргумент:

- Используйте параметр/FORCE: MULTIPLE, чтобы создать выходной файл независимо от того, находит ли ссылка несколько определений для символа.

- Используйте/FORCE: undefine, чтобы создать выходной файл независимо от того, находит ли LINK неопределенный символ. /FORCE: неразрешенный параметр игнорируется, если символ точки входа не разрешен.

/FORCE без аргументов подразумевает как несколько, так и неразрешенные.

Файл, созданный с помощью этого параметра, может работать не так, как ожидалось. Компоновщик не будет выполнять инкрементную компоновку, если указан параметр/FORCE.

Если модуль компилируется с **параметром/CLR**, **/Force** не создаст образ.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Щелкните правой кнопкой мыши проект в **Обозреватель решений** и выберите пункт **свойства**. 

1. Выберите папку **компоновщика**.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в поле **Дополнительные параметры** .

Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
