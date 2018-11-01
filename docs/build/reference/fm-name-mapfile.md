---
title: Параметр /Fm (имя файла сопоставления)
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: 49a3d20aee54b06bae2670be139d748fd2aaca6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469862"
---
# <a name="fm-name-mapfile"></a>Параметр /Fm (имя файла сопоставления)

Предписывает компоновщику создать файл сопоставления, содержащий список сегментов в порядке, в котором они появляются в соответствующий файл .exe или DLL.

## <a name="syntax"></a>Синтаксис

```
/Fmpathname
```

## <a name="remarks"></a>Примечания

По умолчанию получает базовое имя соответствующего файла C или C++ источника с помощью файла сопоставления. Расширения Сопоставления.

Указание **/Fm** действует так же, как если [/Map (Создание файла сопоставления)](../../build/reference/map-generate-mapfile.md) параметр компоновщика.

Если указать [/c (компиляция без связывания)](../../build/reference/c-compile-without-linking.md) запрещающий связывание, **/Fm** не оказывает влияния.

Глобальные символы в файл сопоставления обычно имеют один или несколько таких символов, так как компилятор добавляет подчеркивания имена переменных. Многие из глобальных символов, которые отображаются в файл сопоставления используются внутри компилятора и стандартные библиотеки.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](../../build/reference/output-file-f-options.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Указание пути](../../build/reference/specifying-the-pathname.md)