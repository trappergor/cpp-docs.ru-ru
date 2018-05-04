---
title: '-Zc: auto (выведение типа переменной) | Документы Microsoft'
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:auto
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caa64f64b75145c850c6f6393570dc3f9ba0b0d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (выведение типа переменной)

**/Zc: auto [-]** параметр компилятора сообщает компилятору, как использовать [ключевое слово auto](../../cpp/auto-keyword.md) для объявления переменных. Если указан параметр по умолчанию — **/Zc: auto**, компилятор выводит тип объявленной переменной из выражения инициализации. При указании **/Zc:auto-**, компилятор выделяет переменную для автоматического класса хранения.

## <a name="syntax"></a>Синтаксис

> **/ Zc: auto**[**-**]  

## <a name="remarks"></a>Примечания

Стандарт языка C++ определяет первоначальное и измененное значение ключевого слова `auto`. Прежде чем [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], ключевое слово объявляло переменную в автоматическом классе хранения; то есть, то есть переменную с локальным временем существования. Начиная с [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], ключевое слово выводит тип переменной из выражения инициализации объявления. Используйте **/Zc: auto [-]** компилятора параметр, чтобы компилятор использовал значение исходный или измененный `auto` ключевое слово. **/Zc: auto** включен параметр по умолчанию. [/ Разрешительным-](permissive-standards-conformance.md) параметр не изменяет значение по умолчанию **/Zc: auto**.

Компилятор выдает соответствующее диагностическое сообщение, если использование `auto` ключевое слово противоречит текущего **/Zc: auto** параметр компилятора. Дополнительные сведения см. в разделе [ключевое слово auto](../../cpp/auto-keyword.md). Дополнительные сведения о вопросах соответствия в Visual C++ см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Добавить **/Zc: auto** или **/Zc:auto-** для **Дополнительные параметры:** области.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
[Ключевое слово auto](../../cpp/auto-keyword.md)
