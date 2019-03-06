---
title: /Wp64 (выявление проблем переносимости на 64-разрядные платформы)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
ms.openlocfilehash: b158fb93cb5ea0b43124efe06edb53aebcc0d104
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425579"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (выявление проблем переносимости на 64-разрядные платформы)

Этот параметр компилятора не рекомендуется. В версиях до Visual Studio 2013 это позволяет выявить проблемы с 64-разрядной переносимостью для типов, помеченных также ключевым словом [__w64](../../cpp/w64.md) .

## <a name="syntax"></a>Синтаксис

```
/Wp64
```

## <a name="remarks"></a>Примечания

По умолчанию в версиях Visual Studio до Visual Studio 2013 **/Wp64** компилятора выключен в компиляторе Visual C++, который создает 32-разрядный x86 кода, и на в компиляторе Visual C++, создает 64-разрядная версия, x64 кода.

> [!IMPORTANT]
>  Параметр компилятора [/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) и ключевое слово [__w64](../../cpp/w64.md) являются устаревшими в Visual Studio 2010 и Visual Studio 2012. Они не поддерживаются в версиях начиная с Visual Studio 2013. Если вы преобразуете проект, использующий этот параметр, то во время преобразования он не будет перенесен. Для использования этого параметра в Visual Studio 2010 или Visual Studio 2012 следует ввести параметр компилятора в области **Дополнительные параметры** раздела **Командная строка** в свойствах проекта. Если в командной строке используется параметр компилятора **/Wp64** , компилятор выводит предупреждение командной строки D9002. Обнаруживать конфликты переносимости на 64-разрядные платформы рекомендуется не с помощью этого параметра и ключевого слова, а с помощью компилятора Visual C++, предназначенного для 64-разрядной платформы, и параметра [/W4](../../build/reference/compiler-option-warning-level.md) . Дополнительные сведения см. в разделе [Настройка Visual C++ для 64-разрядная версия, x64 целевых объектов](../../build/configuring-programs-for-64-bit-visual-cpp.md).

Следующие типы переменных проверяются в 32-разрядной операционной системе, как если бы они использовались в 64-разрядной операционной системе:

- int

- long

- указатель

Если приложение регулярно компилируется с помощью компилятора, который создает 64-разрядная версия, x64 код, можно просто отключить **/Wp64** в вашей 32-разрядных компиляциях, так как 64-разрядный компилятор обнаружит все проблемы. Дополнительные сведения о том, как Windows 64-разрядной версии операционной системы см. в разделе [Настройка Visual C++ для 64-разрядная версия, x64 целевых объектов](../../build/configuring-programs-for-64-bit-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта.

   Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Измените поле **Дополнительные параметры** , включив в него параметр **/Wp64**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Настройка Visual C++ для 64-разрядных целевых объектов с архитектурой x64](../../build/configuring-programs-for-64-bit-visual-cpp.md)
