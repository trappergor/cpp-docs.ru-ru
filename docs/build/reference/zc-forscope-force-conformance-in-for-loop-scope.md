---
title: /Zc:forScope (принудительное обеспечение соответствия в области видимости оператора for)
ms.date: 03/06/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
ms.openlocfilehash: 7f98667d3a771994d1b4e54b429f42cb566c102c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316032"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (принудительное обеспечение соответствия в области видимости оператора for)

Использовался для реализации стандартного поведения C++ для циклов [for](../../cpp/for-statement-cpp.md) с расширениями Майкрософт ([/Ze](za-ze-disable-language-extensions.md)).

## <a name="syntax"></a>Синтаксис

> **/ Zc: forScope**[**-**]

## <a name="remarks"></a>Примечания

При стандартном поведении инициализатору цикла **for** позволяется выходить за пределы области после цикла **for** . При использовании **/Zc:forScope-** и [/Ze](za-ze-disable-language-extensions.md)инициализатор цикла **for** остается в пределах области до завершения локальной области.

**/Zc: forScope** включен параметр по умолчанию. **/ Zc: forScope** не затрагивается при [/ permissive-](permissive-standards-conformance.md) параметра.

Параметр **/Zc:forScope-** не рекомендуется к использованию и будет удален в одном из следующих выпусков. Использование **/Zc:forScope-** приводит к созданию предупреждения D9035 о нерекомендуемом элементе.

Приведенный ниже код компилируется при использовании параметра **/Ze** , но не при использовании **/Za**.

```cpp
// zc_forScope.cpp
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp
// C2065, D9035 expected
int main() {
    // Compile by using cl /Zc:forScope- zc_forScope.cpp
    // to compile this non-standard code as-is.
    // Uncomment the following line to resolve C2065 for /Za.
    // int i;
    for (int i = 0; i < 1; i++)
        ;
    i = 20;   // i has already gone out of scope under /Za
}
```

Если используется параметр **/Zc:forScope-**, то каждый раз, когда переменная будет попадать в область из-за ее объявления в предыдущей области, будет выдаваться предупреждение C4288 (оно отключено по умолчанию). Для иллюстрации этого поведения в примере кода необходимо убрать символы `//` для объявления `int i`.

Поведение параметра **/Zc:forScope** во время выполнения можно изменить с помощью директивы pragma [conform](../../preprocessor/conform.md) .

При использовании параметра **/Zc:forScope-** в проекте с существующим файлом PCH выдается предупреждение, параметр **/Zc:forScope-** пропускается, а компиляция продолжается c использованием существующих файлов PCH. Если требуется новый PCH-файл создан, используйте [/Yc (создать предкомпилированный заголовочный файл)](yc-create-precompiled-header-file.md).

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **языка** страницу свойств.

1. Измените свойство **Обеспечение согласования видимости переменных, объявленных в заголовке оператора for** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)<br/>
[/Za, /Ze (отключение расширений языка)](za-ze-disable-language-extensions.md)<br/>
