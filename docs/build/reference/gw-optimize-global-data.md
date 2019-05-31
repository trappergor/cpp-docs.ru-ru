---
title: /Gw (оптимизация глобальных данных)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 8afdb21defbbc8309b27749ab18a40f9555139e5
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450137"
---
# <a name="gw-optimize-global-data"></a>/Gw (оптимизация глобальных данных)

Данные пакета в разделах COMDAT для оптимизации.

## <a name="syntax"></a>Синтаксис

```
/Gw[-]
```

## <a name="remarks"></a>Примечания

**/Gw** предписывает компилятору пакета глобальных данных в отдельных разделах COMDAT. По умолчанию **/Gw** выключен и должен быть явным образом включен. Чтобы явно отключить его, используйте **/Gw-** . Когда оба **/Gw** и [/GL](gl-whole-program-optimization.md) являются включен, компоновщик использует оптимизации всей программы для сравнения COMDAT разделы в нескольких файлах объект исключать неиспользуемые глобальные данные или для слияния идентичные только для чтения глобальные данные. Это может значительно снизить объем итоговый исполняемый файл.

Компиляция и компоновка выполняются отдельно, можно использовать [предотвратят](opt-optimizations.md) параметр компоновщика, чтобы исключить из исполняемого объекта без ссылки глобальных данных в объектных файлах компилируются с **/Gw** параметр.

Можно также использовать [/OPT: ICF](opt-optimizations.md) и [/LTCG](ltcg-link-time-code-generation.md) параметры компоновщика для слияния в исполняемом файле, любой идентичные только для чтения глобальные данные по нескольким файлам объект скомпилирован с **/Gw** параметр.

Дополнительные сведения см. в разделе [Знакомство с /Gw переключатель компилятора](https://devblogs.microsoft.com/cppblog/introducing-gw-compiler-switch/) на C++ блог группы разработчиков.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **C/C++** папки.

1. Выберите **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Gw** и выберите **ОК**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
