---
title: /Os, /Ot (приоритет размера кода или скорости кода)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
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
ms.openlocfilehash: 0eda9461b3ef730e0e0a832aa94a688e03c7e1bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336185"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (приоритет размера кода или скорости кода)

Минимизирует или максимизирует размер EXEs и DLL.

## <a name="syntax"></a>Синтаксис

```
/Os
/Ot
```

## <a name="remarks"></a>Remarks

**/Os** (Favor Small Code) сводит к минимуму размер EXEs и DLL, инструктируя компилятор в пользу размера над скоростью. Компилятор может уменьшить многие конструкции C и C, чтобы функционально схожие последовательности машинного кода. Иногда эти различия предлагают компромиссы размера по сравнению со скоростью. Параметры **/Os** и **/Ot** позволяют указать предпочтение одному по сравнению с другим:

**/Ot** (Favor Fast Code) максимизирует скорость EXEs и DLL, инструктируя компилятор в пользу скорости над размером. (Это по умолчанию.) Компилятор может уменьшить многие конструкции C и C, чтобы функционально схожие последовательности машинного кода. Иногда эти различия предлагают компромиссы по размеру по сравнению со скоростью. Опция **/Ot** подразумевается опцией «Максимальная скорость»[(/O2).](o1-o2-minimize-size-maximize-speed.md) Опция **/O2** сочетает в себе несколько вариантов для создания очень быстрого кода.

Если вы используете **/Os** или **/Ot**, то вы должны также указать [/Og](og-global-optimizations.md) для оптимизации кода.

> [!NOTE]
> Информация, собранная в результате тестовых запусков профилирования, переопределяет оптимизацию, которая в противном случае была бы в силе, если вы **укажете /Ob**, **/Os**, или **/Ot**. Для получения дополнительной [информации, профиль-руководство оптимизации](../profile-guided-optimizations.md).

**Специфика для платформы x86**

Следующий пример кода демонстрирует разницу между вариантами Favor Small Code **(/Os)** и вариантом «Фавор Быстрый код»**(/Ot):**

> [!NOTE]
> Ниже описывается ожидаемое поведение при использовании **/Os** или **/Ot**. Однако поведение компилятора от выпуска к выпуску может привести к различным оптимизациям кода ниже.

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

Как показано в фрагменте машинного кода ниже, когда DIFFER.c компилируется для размера (**/Os**), компилятор реализует выражение умножения в возвратном заявлении явно как умножить для получения короткой, но более медленной последовательности кода:

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

Кроме того, когда DIFFER.c компилируется для скорости (**/Ot**), компилятор реализует `LEA` выражение умножения в отчете о возврате в виде серии сдвигов и инструкций по созданию быстрой, но более длинной последовательности кода:

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**END x86 Специфический**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите на страницу свойства **оптимизации.**

1. Измените свойство **«Размер или скорость».**

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.

## <a name="see-also"></a>См. также раздел

[/O Параметры (Код оптимизации)](o-options-optimize-code.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)
