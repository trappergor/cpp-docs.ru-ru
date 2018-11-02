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
ms.openlocfilehash: 69d26a4e4634ea60457d75bc97d2266036d11e10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525532"
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

- С помощью **/STACK** параметр компоновщика. Дополнительные сведения см. в разделе [/STACK](../../build/reference/stack.md).

- С помощью программы EDITBIN файл .exe. Дополнительные сведения см. в разделе [Справочник ЕDITBIN](../../build/reference/editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)