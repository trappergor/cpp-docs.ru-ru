---
title: /Y- (пропуск параметров предкомпилированного заголовка)
ms.date: 11/04/2016
f1_keywords:
- /y-
helpviewer_keywords:
- Y- compiler option [C++]
- -Y- compiler option [C++]
- /Y- compiler option [C++]
ms.assetid: cfaecb36-58db-46b8-b04d-cca6072b1b7a
ms.openlocfilehash: 8de7de7a4164916b9662e3a78fe00dd0a40cecc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542909"
---
# <a name="y--ignore-precompiled-header-options"></a>/Y- (пропуск параметров предкомпилированного заголовка)

Причины всех остальных `/Y` компилятора параметры нужно игнорировать (и не может сам быть переопределен).

## <a name="syntax"></a>Синтаксис

```
/Y-
```

## <a name="remarks"></a>Примечания

Дополнительные сведения о предкомпилированных заголовках см. в разделе:

- [/Y (предкомпилированные заголовки)](../../build/reference/y-precompiled-headers.md)

- [Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)