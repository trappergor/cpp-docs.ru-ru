---
title: /F (Задание размера стека)
ms.date: 11/04/2016
f1_keywords:
- /f
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
ms.openlocfilehash: 9db595daa7de7820b594a8515ece7481b4382c98
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820420"
---
# <a name="f-set-stack-size"></a>/F (Задание размера стека)

Задает размер стека программы в байтах.

## <a name="syntax"></a>Синтаксис

> **/F** *номер*

## <a name="arguments"></a>Аргументы

*номер*<br/>
Размер стека в байтах.

## <a name="remarks"></a>Примечания

Без этого параметра размер стека по умолчанию до 1 МБ. *Номер* аргумент может быть десятичными или нотации языка. Аргумент находится в диапазоне от 1 до максимального размера стека принят компоновщиком. Компоновщик Округляет указанное значение до ближайшего 4 байт. Расстояние между **/F** и *номер* является необязательным.

Может потребоваться увеличить размер стека, если программа возвращает сообщения о переполнении стека.

Можно также задать размер стека:

- С помощью **/STACK** параметр компоновщика. Дополнительные сведения см. в разделе [/STACK](stack.md).

- С помощью программы EDITBIN файл .exe. Дополнительные сведения см. в разделе [Справочник ЕDITBIN](editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
