---
title: /vmb, /vmg (метод представления)
ms.date: 11/04/2016
f1_keywords:
- /vmb
- /vmg
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
ms.openlocfilehash: 25d24d7f92537f16e36213b8a8fd7b945fda7f5a
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504301"
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (метод представления)

Выберите метод, который используется компилятором для представления указателей на члены класса.

Используйте **/vmb** Если всегда определение класса, прежде чем объявить указатель на член класса.

Используйте **/vmg** для объявления указателя на член класса перед определением класса. Это может понадобиться, если определения элементов в двух различных классов, которые ссылаются друг на друга. Для таких классов взаимно ссылающейся один класс должен ссылаться до ее определения.

## <a name="syntax"></a>Синтаксис

```
/vmb
/vmg
```

## <a name="remarks"></a>Примечания

Можно также использовать [pointers_to_members](../../preprocessor/pointers-to-members.md) или [ключевые слова наследования](../../cpp/inheritance-keywords.md) в код, чтобы указать представление указателя.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
