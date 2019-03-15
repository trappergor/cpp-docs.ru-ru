---
title: / VMM, - vms и - vmv (представление общего назначения)
ms.date: 11/04/2016
f1_keywords:
- /vms
- /vmm
- /vmv
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
ms.openlocfilehash: 7a46cecdbf96ad891ce218df4769a60590e562a9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810046"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms и /vmv (представление общего назначения)

Используется, когда [/vmb, / vmg (метод представления)](vmb-vmg-representation-method.md) выбран в качестве [метод представления](vmb-vmg-representation-method.md). Эти параметры указывают модель наследования определения класса, но не обнаружена.

## <a name="syntax"></a>Синтаксис

```
/vmm
/vms
/vmv
```

## <a name="remarks"></a>Примечания

Данные параметры описаны в следующей таблице.

|Параметр|Описание:|
|------------|-----------------|
|**/vmm**|Указывает наиболее общее представление указателя на член класса, в котором используется множественное наследование.<br /><br /> Соответствующий [ключевое слово наследования](../../cpp/inheritance-keywords.md) и аргумент для [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) — **multiple_inheritance**.<br /><br /> Это представление больше, чем, необходимого для одиночного наследования.<br /><br /> Если модель наследования определения класса, для которой объявлен указатель на член является виртуальной, компилятор создает ошибку.|
|**/vms**|Указывает наиболее общее представление указателя на член класса, в котором использует не наследования или одиночное наследование.<br /><br /> Соответствующий [ключевое слово наследования](../../cpp/inheritance-keywords.md) и аргумент для [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) — **одиночного наследования**.<br /><br /> Это наименьшее возможное представление указателя на член класса.<br /><br /> Если модель наследования определения класса, для которой объявлен указатель на член является несколькими или виртуальными, компилятор выдает ошибку.|
|**/vmv**|Указывает наиболее общее представление указателя на член класса, в котором используется виртуальное наследование. Он никогда не вызывает ошибку и значение по умолчанию.<br /><br /> Соответствующий [ключевое слово наследования](../../cpp/inheritance-keywords.md) и аргумент для [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) — **virtual_inheritance**.<br /><br /> Этот параметр требует большего размера указателя и дополнительный код для интерпретации указателя в сравнении с другими вариантами.|

При указании одного из этих параметров модели наследования, эту модель используется для всех указателей на члены класса, независимо от их типа наследования или ли курсор объявлен до или после класса. Таким образом, если всегда использовать одиночного наследования классов, можно уменьшить размер кода при компиляции с **/vms**; тем не менее, если вы хотите использовать наиболее общий случай (за счет наибольшее представления данных), компиляция с **/vmv**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[/vmb, /vmg (метод представления)](vmb-vmg-representation-method.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
