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
ms.openlocfilehash: 0808f66c4d4c4e99b3038ea18a1f71f4ebaca89a
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446181"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (компиляция среды выполнения Windows)

Компилирует исходный код для поддержки Microsoft C++ расширения компонентов C++/CX для создания приложений универсальной платформы Windows (UWP).

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
