---
title: /DLL (построение библиотеки DLL)
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: 71696e4ffae91ed1fa8a13e69e75523ce66e8361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546348"
---
# <a name="dll-build-a-dll"></a>/DLL (построение библиотеки DLL)

```
/DLL
```

## <a name="remarks"></a>Примечания

Параметр/DLL создает библиотеку DLL в качестве основного выходного файла. Библиотеки DLL, обычно содержит экспортов, которые могут использоваться другой программой. Указание экспортов, перечислены в порядке предпочтительности использования тремя способами:

1. [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) в исходном коде

1. [ЭКСПОРТОВ](../../build/reference/exports.md) инструкции в DEF-файла

1. [/EXPORT](../../build/reference/export-exports-a-function.md) спецификации в команде LINK

Программа может использовать более одного метода.

Другой способ построения библиотеки DLL — с помощью **БИБЛИОТЕКИ** оператор определения модуля. Параметры/Base и/DLL вместе эквивалентны **БИБЛИОТЕКИ** инструкции.

Не использовать этот параметр в среде разработки; Этот параметр предназначен для использования только в командной строке. Этот параметр имеет значение при создании проекта библиотеки DLL с помощью мастера приложений.

Обратите внимание на то, что при создании библиотеки импорта в предварительном перед созданием файла DLL, необходимо передать тот же набор объектных файлов при построении библиотеки DLL, как Вы передали при сборке библиотеки импорта.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **свойства конфигурации** папки.

1. Нажмите кнопку **Общие** страницу свойств.

1. Изменить **тип конфигурации** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)