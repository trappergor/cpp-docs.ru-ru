---
title: -Os, -Ot (приоритет размера кода или скорости кода) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
dev_langs:
- C++
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d74f313caec7ecb98faa3988e8e0dd59847917d5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381521"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (приоритет размера кода или скорости кода)

Свертывает или развертывает размер exe-и DLL-библиотеки.

## <a name="syntax"></a>Синтаксис

```
/Os
/Ot
```

## <a name="remarks"></a>Примечания

**/OS** (приоритет размера кода) минимизирует размер exe-файлы и DLL-файлов, предписывая компилятору предпочитать размер скорости. Компилятор может сократить многие конструкции C и C++ для функциональных возможностей схожих последовательность машинного кода. Иногда эти различия обеспечивают компромиссы или скоростью. **/Os** и **/Ot** параметры позволяют указать предпочтение отдается:

**/Ot** (приоритет скорости кода) повышает скорость файлы exe и DLL-файлов, предписывая компилятору предпочитать скорость и размер. (Это значение по умолчанию). Компилятор может сократить многие конструкции C и C++ для функциональных возможностей схожих последовательность машинного кода. В некоторых случаях эти различия обеспечивают компромиссы или скоростью. Параметр /Ot подразумевается Наибольшая скорость ([/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) параметр. **/O2** объединяет несколько возможностей для создания кода, очень быстро.

Если вы используете **/Os** или **/Ot**, то необходимо также указать [/Og](../../build/reference/og-global-optimizations.md) для оптимизации кода.

> [!NOTE]
>  Сведения, собранные из тестовых запусков профилирования, переопределяют оптимизации, которые бы в противном случае вступят в силу, если указать **/Ob**, **/Os**, или **/Ot**. Дополнительные сведения [профильной оптимизации](../../build/reference/profile-guided-optimizations.md).

**x86 конкретных**

В следующем примере кода демонстрируется различие между приоритет размера кода (**/Os**) параметры и или скорости кода (**/Ot**) параметра:

> [!NOTE]
>  Далее описаны ожидаемое поведение при использовании **/Os** или **/Ot**. Тем не менее поведение компилятора от выпуска к выпуску может привести к разных оптимизаций для приведенный ниже код.

```
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

Как показано в следующем фрагменте машинного кода, когда DIFFER.c предпочтением размер (**/Os**), компилятор реализует выражение в операторе return умножения явным образом как умножение, для создания последовательности короткое, но медленнее кода:

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

Кроме того, когда DIFFER.c предпочтением скорости (**/Ot**), компилятор реализует умножение выражение в операторе return как ряд shift и `LEA` инструкции для создания быстрых, но больше последовательности кода:

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**КОНЕЦ x86 конкретных**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **оптимизации** страницу свойств.

1. Изменить **предпочитать размер или скорость** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)