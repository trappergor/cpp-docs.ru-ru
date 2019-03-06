---
title: /Gw (оптимизация глобальных данных)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: d2c7d8d9a3b3bb877fcf7f4418f3ed20a90a9a11
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420132"
---
# <a name="gw-optimize-global-data"></a>/Gw (оптимизация глобальных данных)

Данные пакета в разделах COMDAT для оптимизации.

## <a name="syntax"></a>Синтаксис

```
/Gw[-]
```

## <a name="remarks"></a>Примечания

**/Gw** предписывает компилятору пакета глобальных данных в отдельных разделах COMDAT. По умолчанию **/Gw** выключен и должен быть явным образом включен. Чтобы явно отключить его, используйте **/Gw-**. Когда оба **/Gw** и [/GL](../../build/reference/gl-whole-program-optimization.md) являются включен, компоновщик использует оптимизации всей программы для сравнения COMDAT разделы в нескольких файлах объект исключать неиспользуемые глобальные данные или для слияния идентичные только для чтения глобальные данные. Это может значительно снизить объем итоговый исполняемый файл.

Компиляция и компоновка выполняются отдельно, можно использовать [предотвратят](../../build/reference/opt-optimizations.md) параметр компоновщика, чтобы исключить из исполняемого объекта без ссылки глобальных данных в объектных файлах компилируются с **/Gw** параметр.

Можно также использовать [/OPT: ICF](../../build/reference/opt-optimizations.md) и [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) параметры компоновщика для слияния в исполняемом файле, любой идентичные только для чтения глобальные данные по нескольким файлам объект скомпилирован с **/Gw** параметр.

Дополнительные сведения см. в разделе [Знакомство с /Gw переключатель компилятора](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) блоге группы разработчиков Visual C++.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **C/C++** папки.

1. Выберите **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Gw** и выберите **ОК**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
