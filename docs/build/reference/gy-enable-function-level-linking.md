---
title: /Gy (включение компоновки на уровне функций)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 368bd469a303222ef4d5177677de4940e402b6de
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413112"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (включение компоновки на уровне функций)

Компилятор может упаковывать отдельные функции в форме упакованных функций (COMDAT).

## <a name="syntax"></a>Синтаксис

```
/Gy[-]
```

## <a name="remarks"></a>Примечания

Компоновщик требует, что функции упаковывать отдельно как COMDAT, чтобы исключить или упорядочить отдельные функции в файл DLL или .exe.

Можно использовать параметр компоновщика [/OPT (оптимизации)](../../build/reference/opt-optimizations.md) исключать неиспользуемые упакованные функции из файла .exe.

Можно использовать параметр компоновщика [/Order (поместить функций по порядку)](../../build/reference/order-put-functions-in-order.md) для включения упакованные функции в указанном порядке, в файл .exe.

Встроенные функции всегда упаковываются, если их экземпляры создаются как вызовы (который, например, происходит, если встроенные является или используется адрес функции). Кроме того определенные в объявлении класса функций-членов C++ упаковываются автоматически; другие функции не являются, и при выборе этого параметра необходим для их компиляции в качестве упакованных функций.

> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) автоматически задает режим работы, изменить и продолжить, **/Gy** параметр.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **создание кода** страницу свойств.

1. Изменить **Включить компоновку на уровне функций** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
