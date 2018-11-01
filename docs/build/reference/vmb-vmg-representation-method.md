---
title: / vmb, - vmg (метод представления)
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
ms.openlocfilehash: 30d15105b9fe502e89f77b19e530d6cc762975a8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505499"
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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)