---
title: /ZW (компиляция среды выполнения Windows)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: 73295866004fd506fd5f06ff25c048d14b821016
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424044"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (компиляция среды выполнения Windows)

Компилирует исходный код для поддержки Visual C++ расширения компонентов C++/CX для создания приложений универсальной платформы Windows (UWP).

При использовании **/ZW** для компиляции, всегда указывайте **/EHsc** также.

## <a name="syntax"></a>Синтаксис

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>Аргументы

**nostdlib**<br/>
Указывает на то, что Platform.winmd, Windows.Foundation.winmd и другие файлы метаданных Windows по умолчанию (WINMD) не включаются в компиляцию автоматически. Вместо этого необходимо использовать [/FU (имя принудительно #using файла)](fu-name-forced-hash-using-file.md) параметр компилятора, чтобы явным образом указать файлы метаданных Windows.

## <a name="remarks"></a>Примечания

При указании **/ZW** параметр, компилятор поддерживает следующие функции:

- Необходимые метаданные файлов, пространств имен, типов данных и функций, которые необходимы приложению для выполнения в среде выполнения Windows.

- Автоматический подсчет ссылок на объекты среды выполнения Windows и автоматическое удаление объекта, когда его счетчик ссылок становится равен нулю.

Так как Инкрементный компоновщик не поддерживает метаданные Windows, входящие в OBJ-файлов с помощью **/ZW** параметра устаревших [/Gm (включение минимального перепостроения)](gm-enable-minimal-rebuild.md) не совместим с **/Zw**.

Дополнительные сведения см. в разделе [Справочник по языку Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).

## <a name="requirements"></a>Требования

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
