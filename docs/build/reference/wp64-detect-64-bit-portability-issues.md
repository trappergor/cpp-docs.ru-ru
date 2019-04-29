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
ms.openlocfilehash: 5a3cdaf85fa4dc05ece54fc630cb69fc93650e6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316552"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (выявление проблем переносимости на 64-разрядные платформы)

Этот параметр компилятора не рекомендуется. В версиях до Visual Studio 2013 это позволяет выявить проблемы с 64-разрядной переносимостью для типов, помеченных также ключевым словом [__w64](../../cpp/w64.md) .

## <a name="syntax"></a>Синтаксис

```
/Wp64
```

## <a name="remarks"></a>Примечания

По умолчанию в версиях Visual Studio до Visual Studio 2013 **/Wp64** компилятора выключен в компилятор MSVC, который создает 32-разрядный x86 кода, и в компилятор MSVC, создает 64-разрядная версия, x64 кода.

> [!IMPORTANT]
>  Параметр компилятора [/Wp64](wp64-detect-64-bit-portability-issues.md) и ключевое слово [__w64](../../cpp/w64.md) являются устаревшими в Visual Studio 2010 и Visual Studio 2012. Они не поддерживаются в версиях начиная с Visual Studio 2013. Если вы преобразуете проект, использующий этот параметр, то во время преобразования он не будет перенесен. Для использования этого параметра в Visual Studio 2010 или Visual Studio 2012 следует ввести параметр компилятора в области **Дополнительные параметры** раздела **Командная строка** в свойствах проекта. Если в командной строке используется параметр компилятора **/Wp64** , компилятор выводит предупреждение командной строки D9002. Вместо использования этого параметра и ключевого слова для обнаружения проблем переносимости на 64-разрядной платформы, использовать компилятор MSVC, предназначенный для 64-разрядной платформы и укажите [/W4](compiler-option-warning-level.md) параметр. Дополнительные сведения см. в разделе [C++, Настройка проектов для 64-разрядных систем, x64 целевых объектов](../configuring-programs-for-64-bit-visual-cpp.md).

Следующие типы переменных проверяются в 32-разрядной операционной системе, как если бы они использовались в 64-разрядной операционной системе:

- int

- long

- указатель

Если приложение регулярно компилируется с помощью компилятора, который создает 64-разрядная версия, x64 код, можно просто отключить **/Wp64** в вашей 32-разрядных компиляциях, так как 64-разрядный компилятор обнаружит все проблемы. Дополнительные сведения о том, как Windows 64-разрядной версии операционной системы см. в разделе [C++, Настройка проектов для 64-разрядных систем, x64 целевых объектов](../configuring-programs-for-64-bit-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта.

   Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Измените поле **Дополнительные параметры** , включив в него параметр **/Wp64**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Настройка проектов C++ для 64-разрядная версия, x64 целевых объектов](../configuring-programs-for-64-bit-visual-cpp.md)
